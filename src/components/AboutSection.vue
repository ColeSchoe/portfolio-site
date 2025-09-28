<template>
    <div class="container">
        <h1 class="about-header">About</h1>
        <div class="photo">PHOTO PLACEHOLDER</div>
        <p>Always enthusiastic to learn more, I have a wide background when it comes to the 
            projects I have worked on. I find myself doing my best work in projects that ask me to
            solve new problems and learn something new. While I have formal education in Computer Science,
            my experience has exposed me to many frameworks, programming lauguages, and project settings. 
            This can be seen below in the following sections covering my education and projects. If I'm not 
            working on a project you can find me going for a run, spending time with friends and loved ones, 
            or playing videogames.
        </p>
    </div>
</template>

<style scoped>
    .container {
        padding: 15vh 0;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 4rem;
    }

    .about-header {
        font-weight: 500;
        font-style: italic;
    }

    p {
        max-width: 50%;
    }
</style>