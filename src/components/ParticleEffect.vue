<script setup>
import {ref, onMounted, onBeforeUnmount, reactive} from 'vue';

const canvasRef = ref(null);
const canvasContainerRef = ref(null);
const context = ref(null);
const shapes = ref([]);
const canvasSize = reactive({w: 0, h: 0});
const dpr = window.devicePixelRatio || 1;

onMounted(() => {
    if (canvasRef.value) {
        context.value = canvasRef.value.getContext('2d');
    }
    initCanvas();
    animate();
    window.addEventListener('resize', initCanvas);
})

onBeforeUnmount(() => {
    window.removeEventListener('resize', initCanvas);
})

const initCanvas = () => {
    resizeCanvas();
    drawParticles();
}

const resizeCanvas = () => {
    if (canvasContainerRef.value && canvasRef.value && context.value) {
        shapes.value.length = 0;
        canvasSize.w = canvasContainerRef.value.offsetWidth;
        canvasSize.h = canvasContainerRef.value.offsetHeight;
        canvasRef.value.width = canvasSize.w * dpr;
        canvasRef.value.height = canvasSize.h * dpr;
        canvasRef.value.style.width = canvasSize.w + 'px';
        canvasRef.value.style.height = canvasSize.h + 'px';
        context.value.scale(dpr, dpr);
    }
}

const triangleParams = () => {
    const x = Math.floor(Math.random() * canvasSize.w);
    const y = Math.floor(Math.random() * canvasSize.h);
    const translateX = 0;
    const translateY = 0;
    const size = Math.floor(Math.random() * 15) + 1;
    const alpha = 0;
    const targetAlpha = parseFloat((Math.random() * 0.6 + 0.1).toFixed(1)); // 0.1 to 0.7
    const dx = (Math.random() - 0.5) * 0.2;
    const dy = (Math.random() - 0.5) * 0.2;
    const magnetism = 0.1 + Math.random() * 4;
    const rotation = Math.random() * 360;
    return { x, y, translateX, translateY, size, alpha, targetAlpha, dx, dy, magnetism, rotation };
}

const drawTriangle = (triangle, update = false) => {
    if (context.value) {
        const {x, y, translateX, translateY, size, alpha, rotation } = triangle;

        // Move triangle
        context.value.translate(translateX, translateY);

        // Drawing triangle
        context.value.beginPath();

        // Using parametric equations of a circle to find x and y
        // --  x = r*cos(rotation), y = r*sin(rotation) --
        context.value.moveTo(x + (size * Math.cos(rotation)), y + (size * Math.sin(rotation))); // Top
        context.value.lineTo(x + (size * Math.cos(rotation-90)), y + (size * Math.sin(rotation-90))); // Bottom-left
        context.value.lineTo(x + (size * Math.cos(rotation+90)), y + (size * Math.sin(rotation+90))); // Bottom-right

        context.value.closePath(); // Connect last point to first point, so bottom right to top

        // Filling triangle
        context.value.fillStyle = `rgba(138, 154, 91, ${alpha})`;
        context.value.fill();
        context.value.setTransform(dpr, 0, 0, dpr, 0, 0);

        if (!update) {
            shapes.value.push(triangle);
        }
    }
}

const clearContext = () => {
    if (context.value) {
        context.value.clearRect(0, 0, canvasSize.w, canvasSize.h);
    }
}

const drawParticles = () => {
    clearContext();
    const particleCount = props.quantity;

    for (let i = 0; i < particleCount; i++) {
        const triangle = triangleParams();
        drawTriangle(triangle);
    }
}

const remapValue = (value,start1, end1, start2, end2) => {
    const remapped = ((value - start1) * (end2 - start2)) / (end1 - start1) + start2
    return remapped > 0 ? remapped : 0
}

const animate = () => {
    clearContext()
    shapes.value.forEach((shape, i) => {
        // Handle the alpha value based on how close it is to element edge
        const edge = [
        shape.x + shape.translateX - shape.size, // distance from left edge
        canvasSize.w - shape.x - shape.translateX - shape.size, // distance from right edge
        shape.y + shape.translateY - shape.size, // distance from top edge
        canvasSize.h - shape.y - shape.translateY - shape.size, // distance from bottom edge
        ]
        const closestEdge = edge.reduce((a, b) => Math.min(a, b))
        const remapClosestEdge = parseFloat(remapValue(closestEdge, 0, 20, 0, 1).toFixed(2))
        if (remapClosestEdge > 1) {
        shape.alpha += 0.02
        if (shape.alpha > shape.targetAlpha) shape.alpha = shape.targetAlpha
        } else {
        shape.alpha = shape.targetAlpha * remapClosestEdge
        }

        // Update location
        shape.x += shape.dx
        shape.y += shape.dy
        shape.translateX += ((shape.dx / (props.staticity / shape.magnetism)) - shape.translateX) / props.ease
        shape.translateY += ((shape.dy / (props.staticity / shape.magnetism)) - shape.translateY) / props.ease

        // shape gets out of the canvas
        if (
        shape.x < -shape.size ||
        shape.x > canvasSize.w + shape.size ||
        shape.y < -shape.size ||
        shape.y > canvasSize.h + shape.size
        ) {
        // remove the shape from the array
        shapes.value.splice(i, 1)
        // create a new shape
        const newShape = triangleParams()
        drawTriangle(newShape)
        // update the shape position
        } else {
        drawTriangle(
            {
            ...shape,
            x: shape.x,
            y: shape.y,
            translateX: shape.translateX,
            translateY: shape.translateY,
            alpha: shape.alpha,
            rotation: shape.rotation,
            },
            true
        )
        }
    })
    window.requestAnimationFrame(animate)
}

const props = defineProps({
    quantity: {
        type: Number,
        default: 100,
    },
    staticity: {
        type: Number,
        default: 50,
    },
    ease: {
        type: Number,
        default: 50,
    }
})

</script>

<template>
    <div ref="canvasContainerRef" aria-hidden="true">
        <canvas ref="canvasRef"></canvas>
    </div>
</template>