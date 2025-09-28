<script setup>
    function scrollToElement(id) {
        const element = document.getElementById(id);
        if (element) {
            element.scrollIntoView({behavior: "smooth"});
        }
    }
</script>

<template>
    <div class="container">
        <h1>Hi! I'm Cole Schoenbauer, a software developer.</h1>
        <button @click="scrollToElement('about-section')">More About Me</button>
    </div>
</template>

<style scoped>
    .container {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
        height: 100vh;
        gap: 40px;

        font-size: 1.4rem;
    }

    button {
        border: none;

        font: inherit;
        background-color: var(--color-background-mute);
        color: var(--color-text);
        padding: .5rem 1.5rem;
        border-radius: 20px;
    }

    button:hover {
        color: var(--color-text-dark);
        transition-duration: 500ms;
        cursor: pointer;
    }
</style>