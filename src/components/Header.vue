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
        <button id="welcome-section-button" @click="scrollToElement('welcome-section')"><h2>Welcome</h2></button>
        <button id="about-section-button" @click="scrollToElement('about-section')"><h2>About</h2></button>
        <button id="education-section-button" @click="scrollToElement('education-section')"><h2>Education</h2></button>
        <button id="projects-section-button" @click="scrollToElement('projects-section')"><h2>Projects</h2></button>
        <button id="contact-section-button" @click="scrollToElement('contact-section')"><h2>Contact</h2></button>
    </div>
</template>

<style scoped>
    .container {
        display: flex;
        justify-content: end;
        gap: 3%;
        padding: 3vh 0px;
        padding-right: 10%;
        background-color: var(--color-background-mute);
    }

    button {
        all: unset;
    }

    button:hover {
        color: var(--main-green);
        transition-duration: 500ms;
        cursor: pointer;
    }
</style>