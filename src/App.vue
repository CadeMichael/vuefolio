<script setup>
 import Navbar from './components/Navbar.vue';
 import Welcome from './components/Welcome.vue';
 import About from './components/About.vue';
 import Projects from './components/Projects.vue';
 import Resume from './components/Resume.vue';
 import Footer from './components/Footer.vue';
</script>

<template>
    <Navbar />
    <div class="">
        <div class="container mx-auto" id="welcome">
            <Welcome />
        </div>
        <div class="container mx-auto" id="about">
            <div>
                <div class="divider lg:hidden text-2xl text-secondary">About</div> 
                <div class="hidden lg:block m-4 text-3xl text-secondary font-bold">About</div> 
            </div>
            <About />
        </div>
        <div class="container mx-auto" id="projects">
            <div>
                <div class="divider lg:hidden text-2xl text-secondary">Projects</div> 
                <div class="hidden lg:block m-4 text-3xl text-secondary font-bold">Projects</div> 
            </div>
            <Projects />
        </div>
        <div class="container mx-auto" id="resume">
            <div>
                <div class="divider lg:hidden text-2xl text-secondary">Resume</div> 
                <div class="hidden lg:block m-4 text-3xl text-secondary font-bold">Resume</div> 
            </div>
            <Resume />
        </div>
    </div>
    <Footer />
</template>

<style scoped>
</style>
