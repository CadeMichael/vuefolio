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
         document.activeElement.blur();
     } else {
    console.warn(`Element with ID ${componentId} not found`);
  }
 }
</script>

<template>
	<div class="navbar bg-neutral rounded shadow-xl">
		<div class="navbar-start">
			<div id="navdrop" class="dropdown">
				<div tabindex="0" role="button" class="btn btn-ghost lg:hidden">
					<svg xmlns="http://www.w3.org/2000/svg" class="h-5 w-5" fill="none" viewBox="0 0 24 24" stroke="currentColor"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h8m-8 6h16" /></svg>
				</div>
				<ul class="menu menu-sm dropdown-content mt-3 z-[1] p-2 shadow bg-neutral rounded-box w-52">
					<li><button @click="scrollToComponent('about')">About</button></li>
					<li><button @click="scrollToComponent('projects')">Projects</button></li>
					<li><button @click="scrollToComponent('resume')">Resume</button></li>
				</ul>
			</div>
		<div tabindex="0" class="hidden lg:avatar">
			<div class="w-10 mask mask-squircle">
				<img :src="getImageUrl('profile','jpg')" alt="Tailwind CSS Navbar component" />
			</div>
		</div>
		</div>
		<div class="navbar-center">
			<a class="ml-2 hidden lg:btn lg:btn-ghost lg:text-xl">Cade Lueker</a>
		</div>
		<div class="lg:hidden navbar-end">
			<a class="lm-2 btn btn-ghost text-xl">Cade Lueker</a>
		</div>
		<div class="navbar-end hidden lg:flex">
			<ul class="menu menu-horizontal px-1">
				<li><a @click="scrollToComponent('about')">About</a></li>
				<li><a @click="scrollToComponent('projects')">Projects</a></li>
				<li><a @click="scrollToComponent('resume')">Resume</a></li>
			</ul>
		</div>
	</div>
</template>

<style scoped>
</style>
