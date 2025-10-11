<script setup>
import ParticleEffect from './ParticleEffect.vue';

function scrollToElement(id) {
    const element = document.getElementById(id);
    if (element) {
        element.scrollIntoView({behavior: "smooth"});
    }
}
</script>

<template>
    <div class="container">
        <ParticleEffect id="welcome-canvas" :quantity="150"></ParticleEffect>
        <div id="canvas-overlay">
            <h1>Hi! I'm Cole Schoenbauer, a software developer.</h1>
            <button @click="scrollToElement('about-section')">More About Me</button>
        </div>
    </div>
</template>

<style scoped>
    .container {
        height: 100vh;
        position: relative;
    }

    #welcome-canvas {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 1;

        width: 100%;
        height: 100%;
    }

    #canvas-overlay {
        position: absolute;
        top: 0;
        left: 0;
        z-index: 2;
        width: 100%;
        height: 100%;

        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
        gap: 40px;

        font-size: 1.4rem;
        text-align: center;
    }

    button {
        border: 1px solid transparent;

        font: inherit;
        background-color: var(--color-background-mute);
        color: var(--color-text);
        padding: .5rem 1.5rem;
        border-radius: 20px;

        display: flex;
        align-items: center;
        gap: 10px;
    }

    button:hover {
        color: var(--main-green);
        transition-duration: 500ms;
        cursor: pointer;
    }

    button:active {
        border: 1px solid var(--main-green);
        background-image: radial-gradient(circle at center, var(--color-background-brightest), var(--color-background-mute));
        transition-duration: 50ms;
    }
</style>