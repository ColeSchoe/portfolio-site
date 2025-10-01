<script setup>
    function download() {
        const filename = "Cole-Schoenbauer-Resume.pdf";
        const element = document.createElement('a');
        element.setAttribute('href', 'data/application/src/assets/Cole-Schoenbauer-9-25.pdf');
        element.setAttribute('download', filename);

        element.style.display = "none";
        document.body.appendChild(element);

        element.click();
        document.body.removeChild(element);
    }
</script>

<template>
    <div class="container">
        <h1 class="contact-header">Contact</h1>
        <div class="contact-info">
            <div class="email-info">
                <img src="../assets/mail.svg" alt="">
                <p>coleschoenbauer@gmail.com</p>
            </div>
            <a class="resume" href="src\assets\Cole-Schoenbauer-9-2025.pdf" download>Download My Resume</a>
            <div class="web-shortcuts">
                <a target="_blank" href="https://www.linkedin.com/in/cole-schoenbauer-488963251/"><img src="../assets/LinkedIn_icon.png" alt="Link to my LinkedIn"></a>
                <a target="_blank" href="https://github.com/ColeSchoe"><img src="../assets/github-icon.png" alt="Link to my GitHub"></a>
            </div>
        </div>
    </div>
</template>

<style scoped>
    .container {
        padding-top: 15vh;
        height: 100vh;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 4rem;
    }

    .contact-header {
        font-weight: 500;
        font-style: italic;
    }

    .contact-info {
        display: flex;
        flex-direction: column;
        gap: 3rem;
        align-items: center;
    }

    .email-info {
        display: flex;
        gap: 1rem;
        align-items: center;
    }

    .resume {
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

    .resume:hover {
        color: var(--main-green);
        transition-duration: 500ms;
        cursor: pointer;
    }

    .resume:active {
        border: 1px solid var(--main-green);
        background-color: var(--color-background-soft);
        transition: background-color .2s;
    }

    .web-shortcuts {
        display: flex;
        justify-content: center;
        gap: 2rem;
    }

    .web-shortcuts img {
        max-width: 96px;
        height: auto;
        margin: auto;

        border-radius: 20px;
    }
</style>