<template>
    <div class="container">
        <h1 class="education-header">Education</h1>
        <div class="education-information">
            <h2>Bachelor's of Science, Computer Science</h2>
            <h3>Minor in Mathematics</h3>
            <h3>Minnesota State University, Mankato</h3>
            <h3>Mankato, MN, United States</h3>
            <h3>Graduated May 2024, GPA: 3.78</h3>
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

    .education-header {
        font-weight: 500;
        font-style: italic;
    }

    .education-information {
        display: flex;
        flex-direction: column;
        align-items: center;

         /* Simple gradient - diagonal */
        background-image: linear-gradient(to top left, var(--color-background-soft), var(--color-background-bright));

        /* background-color: var(--color-background-soft); */
        border-radius: 20px;
        padding: 2rem;
    }

    h2 {
        font-weight: 500;
    }
</style>