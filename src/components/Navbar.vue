<script setup>
 import {ref} from 'vue';
 function getImageUrl(name, ext) {
	 return new URL(`../assets/${name}.jpg`, import.meta.url).href
 }
 // Scroll to the target element when a link is clicked
 function scrollToComponent(componentId) {
     const element = document.getElementById(componentId);
     if (element) {
         element.scrollIntoView({ behavior: 'smooth' });
     } else {
    console.warn(`Element with ID ${componentId} not found`);
  }
 }
</script>

<template>
    <div class="drawer">
        <input id="my-drawer-3" type="checkbox" class="drawer-toggle" /> 
        <div class="drawer-content">
            <div class="navbar bg-neutral rounded shadow-xl">
                <div class="flex-none lg:hidden">
                    <label for="my-drawer-3" aria-label="open sidebar" class="btn btn-square btn-ghost">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" class="inline-block w-6 h-6 stroke-current"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path></svg>
                    </label>
                </div>
                <div class="navbar-start mx-auto">
                    <a class="ml-2 hidden lg:btn lg:btn-ghost lg:text-xl">Cade Lueker</a>
                </div>
                <div class="lg:hidden navbar-end">
                    <a class="lm-2 btn btn-ghost text-xl">Cade Lueker</a>
                </div>
                <div class="navbar-end hidden lg:ml-auto lg:flex">
                    <ul class="menu menu-horizontal px-1">
                        <li><a @click="scrollToComponent('about')">About</a></li>
                        <li><a @click="scrollToComponent('projects')">Projects</a></li>
                        <li><a @click="scrollToComponent('resume')">Resume</a></li>
                    </ul>
                </div>
            </div>
        </div>
        <div class="drawer-side z-10">
            <label for="my-drawer-3" aria-label="close sidebar" class="drawer-overlay"></label> 
            <ul class="menu p-4 flex min-h-full bg-base-200">
                <a @click="scrollToComponent('about')" class="btn"><li>About</li></a>
                <a @click="scrollToComponent('projects')" class="btn"><li>Projects</li></a>
                <a @click="scrollToComponent('resume')" class="btn"><li>Resume</li></a>
            </ul>
        </div>
    </div>
</template>

<style scoped>
</style>
