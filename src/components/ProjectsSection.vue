<template>
    <div class="container">
        <h1 class="projects-header">Projects</h1>
        <div class="project">
            <div class="info">
                <h2>GPU Price Checker</h2>
                <p>A series of Python scripts using Selenium to gather pricing data and availability 
                    on RTX 5090 websites from common US retailers.
                </p>
                <a target="_blank" href="https://github.com/ColeSchoe/rtx5090-status-checker">See More</a>
            </div>
            
            <img src="../assets/rtx5090-image.jpg" alt="NVIDIA RTX 5090 Photo">
        </div>

        <div class="project">
            <div class="info">
                <h2>VR 3D Music Mixer</h2>
                <p> Led a small team utilizing Unity, the OpenXR library, and Wwise audio middleware
                    to develop a VR prototype for mixing music in three-dimensional space. 
                </p>
            </div>
            
            <img src="../assets/vr-app-screenshot.png" alt="Photo of gameplay of a VR game prototype">
        </div>

        <div class="project">
            <div class="info">
                <h2>Business Info Collector</h2>
                <p>Built web scraping tools using Python and Selenium to automatically extract 
                    business data from websites. Designed a data cleaning pipeline to transform 
                    raw data into structured formats for client use.
                </p>
            </div>
            
            <img src="../assets/business-info-scraper.png" alt="A Chrome window being directed by Selenium Webdriver">
        </div>

        <div class="project">
            <div class="info">
                <h2>WIP Budgeting App Prototype</h2>
                <p>Working within a team of four to create a webapp that assists users with self-budgeting.
                    With a Vue.js frontend, I am specializing in design and implementation of the frontend.
                    Contributed to the implementation of Time-based One-time Password and JWT interactions
                    with the FastAPI backend.
                </p>
            </div>
            
            <img src="../assets/budgeting-dashboard.png" alt="Budgeting Webapp Dashboard">
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

    .projects-header {
        font-weight: 500;
        font-style: italic;
    }

    .project {
        min-height: 60vh;
        max-height: 100vh;
        max-width: 80%;
        padding: 0 2rem;

        display: flex;
        align-items: center;
        gap: 2rem;

        background-color: var(--color-background-soft);
        border-radius: 20px;

        overflow: hidden;
        text-overflow: ellipsis;
    }

    .project img {
        border-radius: 15px;
        max-width: 540px;
        height: auto;
        margin: auto;
    }

    .info {
        display: flex;
        flex-direction: column;
        align-items: start;
        gap: 1rem;
    }

    .info h2 {
        flex: 1;
    }

    .info a {
        font-weight: 500;
        color: var(--main-green);
        padding: .4rem 1rem;
        border-radius: 10px;
        padding-left: 0;
    }

    .info a:hover {
        color: var(--color-text);
        transition: color .5s;
    }

    h2 {
        font-weight: 500;
        font-style: italic;
    }
</style>