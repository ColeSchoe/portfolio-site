<template>
    <div class="container">
        <h1 class="about-header">About</h1>
        <img id="my-photo" src="../assets/me.jpg" alt="A photo of me">
        <p>&emsp;Always enthusiastic to learn more, I have a wide background when it comes to the 
            projects I have worked on. I find myself doing my best work in projects that ask me to
            solve new problems and learn something new. While I have formal education in Computer Science,
            my experience has exposed me to many frameworks, programming lauguages, and project settings. 
            If I'm not working on a project you can find me going for a run, spending time with friends 
            and loved ones, or playing videogames. You can see a few of the 
            programming languages, tools, and frameworks that I'm familiar with below. 
            A more detailed explanation of my experience can also be seen below in the following sections 
            covering my education and projects.
        </p>
        <div class="tools">
            <div class="tool-row">
                <div class="tool">
                    JavaScript
                    <img src="../assets/tools-assets/jslogo.png" alt="JavaScript Logo">
                </div>
                <div class="tool">
                    HTML
                    <img src="../assets/tools-assets/html-logo.png" alt="HTML Logo">
                </div>
                <div class="tool">
                    CSS
                    <img src="../assets/tools-assets/css-logo.png" alt="CSS Logo">
                </div>
            </div>

            <div class="tool-row">
                <div class="tool">
                    Vue.js
                    <img src="../assets/tools-assets/vuejs-logo.png" alt="Vue.js Logo">
                </div>
                <div class="tool">
                    C#
                    <img src="../assets/tools-assets/csharp-logo.png" alt="C# Logo">
                </div>
                <div class="tool">
                    C++
                    <img src="../assets/tools-assets/cpp-logo.png" alt="C++ Logo">
                </div>
                <div class="tool">
                    Java
                    <img src="../assets/tools-assets/java-logo.png" alt="Java Logo">
                </div>
            </div>

            <div class="tool-row">
                <div class="tool">
                    Python
                    <img src="../assets/tools-assets/python-logo.png" alt="Python Logo">
                </div>
                <div class="tool">
                    VS Code
                    <img src="../assets/tools-assets/vscode-logo.png" alt="VS Code Logo">
                </div>
                <div class="tool">
                    SQL
                    <img src="../assets/tools-assets/sql-logo.png" alt="SQL Logo">
                </div>
            </div>
            
        </div>
    </div>
</template>

<style scoped>
    .container {
        padding-top: 15vh;

        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 4rem;
    }

    .about-header {
        font-weight: 500;
        font-style: italic;
    }

    #my-photo {
        max-height: 30vh;
        width: auto;
        border-radius: 50%;
    }

    .tools {
        max-height: 90vh;
        display: flex;
        flex-direction: column;
        gap: 5vh;
        padding: 10vh 0;
    }

    .tool-row {
        display: flex;
        flex-direction: row;
        justify-content: center;
        gap:4rem;
    }

    .tool {
        display: flex;
        flex-direction: column;
        align-items: center;
        font-weight: 500;
        font-style: italic;
        gap: 10px;

        background-color: var(--color-background-soft);
        border-radius: 20px;
        padding: 1rem;

        /* Simple gradient - diagonal */
        /* background-image: linear-gradient(to bottom right, var(--color-background-soft), var(--color-background-mute)); */

        /* Transparency gradient */
        /* background-image: linear-gradient(to right, rgba(34,34,34,0), rgba(34,34,34,1)); */

    }

    .tool:hover {
        background-color: var(--color-background-mute);
        transition: .5s;
    }

    .tool img {
        max-width: 96px;
        height: auto;
        margin: auto;
    }

    p {
        max-width: 50%;
    }
</style>