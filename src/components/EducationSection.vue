<template>
    <div class="container">
        <h1 class="education-header">Education</h1>
        <div class="education-information">
            <h2>Minnesota State University, Mankato</h2>
            <h3>BS Computer Science</h3>
            <h3>Graduated May 2024, GPA: 3.78</h3>
            <h3>Mankato, MN, United States</h3>
        </div>
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

    .education-header {
        font-weight: 500;
        font-style: italic;
    }

    .education-information {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    p {
        max-width: 50%;
    }

    h2 {
        font-weight: 500;
    }
</style>