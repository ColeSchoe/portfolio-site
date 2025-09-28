<script setup>
import WelcomeSection from '@/components/WelcomeSection.vue';
import AboutSection from '@/components/AboutSection.vue';
import EducationSection from '@/components/EducationSection.vue';
import ProjectsSection from '@/components/ProjectsSection.vue';
import ContactSection from '@/components/ContactSection.vue';
import Header from '@/components/Header.vue';
</script>

<template>
  <main>
    <WelcomeSection id="welcome-section"/>
    <Header class="header"></Header>
    <AboutSection id="about-section"/>
    <EducationSection id="education-section"/>
    <ProjectsSection id="projects-section"/>
    <ContactSection id="contact-section"/>
  </main>
</template>

<style scoped>
.header {
  top: 0;
  width: 100%;
  position: sticky;
}
</style>