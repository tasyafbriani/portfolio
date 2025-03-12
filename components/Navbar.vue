<template>
  <nav :class="'fixed top-0 w-full z-50 transition-all duration-300 border-pink-200 dark:border-pink-700 ' + (scrolled ? ' backdrop-blur-md shadow-md' : 'bg-transparent')">
     <div class="max-w-screen-xl flex flex-wrap items-center justify-between mx-auto p-4">
      <nuxt-link to="/" class="flex items-center ml-5">
    <img class="w-10 h-10 mr-3" src="https://img.icons8.com/external-justicon-flat-justicon/64/external-butterfly-woman-day-justicon-flat-justicon.png" alt="external-butterfly-woman-day-justicon-flat-justicon"/>
    <div class="relative overflow-hidden group">
    <div class="flex items-center">
      <span class="text-3xl font-bold text-white transition-transform duration-300 ease-in-out transform group-hover:scale-95 group-hover:text-transparent group-hover:bg-clip-text group-hover:bg-gradient-to-r group-hover:from-fuchsia-500 group-hover:to-rose-600">
        Tasya
      </span>
      <span class="text-3xl font-bold text-white ml-2 opacity-100 group-hover:opacity-0 transition-opacity duration-300">
        Fbriani
      </span>
    </div>
  </div>
  </nuxt-link>
  
  <button
    @click="toggleMobileMenu"
    type="button"
    class="inline-flex items-center p-2 w-10 h-10 justify-center text-sm text-pink-700 rounded-lg md:hidden bg-gradient-to-br from-[#E6D5C3] via-fuchsia-400 to-rose-300 hover:bg-gradient-to-tr transition-all duration-500 focus:outline-none focus:ring-2 focus:ring-pink-200 dark:text-pink-400 dark:hover:bg-gradient-to-tr dark:focus:ring-pink-600"
    aria-controls="navbar-dropdown"
    :aria-expanded="isMobileMenuOpen"
  >
    <span class="sr-only">Open Menu</span>
    <svg class="w-5 h-5" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 17 14">
      <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M1 1h15M1 7h15M1 13h15" />
    </svg>
  </button>   
  
          <div 
    class="w-full md:block md:w-auto
           p-4 rounded-lg
           md:bg-none md:p-0"
    :class="{
      'bg-gradient-to-br from-[#E6D5C3] via-fuchsia-400 to-rose-300': isMobileMenuOpen,
      'bg-none': !isMobileMenuOpen,
      'block': isMobileMenuOpen,
      'hidden': !isMobileMenuOpen
    }"
    id="navbar-dropdown"
  >
    <ul class="flex flex-col font-medium p-4 md:p-0 mt-4 border rounded-lg md:flex-row md:space-x-8 md:mt-0 md:border-0 bg-white/5 md:bg-transparent">
      <li class="py-2 md:py-0">
        <a href="#" @click.prevent="scrollToSection('home')">
          <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent"
            :class="scrolled ? 'text-white dark:text-white' : 'text-white'">
            Home
          </div>
        </a>
      </li>
  
      <li class="py-2 md:py-0">
        <a href="#about" @click.prevent="scrollToSection('about')">
          <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent"
            :class="scrolled ? 'text-white dark:text-white' : 'text-white'">
            About
          </div>
        </a>
      </li>
  
      <li class="py-2 md:py-0">
        <a href="#services" @click.prevent="scrollToSection('services')">
          <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent"
            :class="scrolled ? 'text-white dark:text-white' : 'text-white'">
            Services
          </div>
        </a>
      </li>
  
      <li class="py-2 md:py-0">
        <a href="#projects" @click.prevent="scrollToSection('projects')">
          <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent"
            :class="scrolled ? 'text-white dark:text-white' : 'text-white'">
            Project
          </div>
        </a>
      </li>  
      
      <li class="py-2 md:py-0">
        <a href="#contact" @click.prevent="scrollToSection('contact')">
          <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent"
            :class="scrolled ? 'text-white dark:text-white' : 'text-white'">
            Contact
          </div>
        </a>
      </li>  
  
      <li class="py-2 md:py-0">
    <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent">
      <a class="text-white hover:text-pink-500" href="https://www.instagram.com/tsyafbrni?igsh=MTBkNDh4ZmQyb2I4YQ==" target="_blank">
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path d="M12 2.163c3.204 0 3.584.012 4.85.07 1.366.062 2.633.334 3.608 1.31.975.975 1.248 2.242 1.31 3.608.058 1.266.07 1.646.07 4.85s-.012 3.584-.07 4.85c-.062 1.366-.334 2.633-1.31 3.608-.975.975-2.242 1.248-3.608 1.31-1.266.058-1.646.07-4.85.07s-3.584-.012-4.85-.07c-1.366-.062-2.633-.334-3.608-1.31-.975-.975-1.248-2.242-1.31-3.608-.058-1.266-.07-1.646-.07-4.85s.012-3.584.07-4.85c.062-1.366.334-2.633 1.31-3.608.975-.975 2.242-1.248 3.608-1.31 1.266-.058 1.646-.07 4.85-.07zm0-2.163c-3.259 0-3.667.014-4.947.072-1.281.058-2.418.27-3.29.542-.872.272-1.611.63-2.347 1.366-.736.736-1.094 1.475-1.366 2.347-.272.872-.484 2.009-.542 3.29-.058 1.28-.072 1.688-.072 4.947s.014 3.667.072 4.947c.058 1.281.27 2.418.542 3.29.272.872.63 1.611 1.366 2.347.736.736 1.475 1.094 2.347 1.366.872.272 2.009.484 3.29.542 1.28.058 1.688.072 4.947.072s3.667-.014 4.947-.072c1.281-.058 2.418-.27 3.29-.542.872-.272 1.611-.63 2.347-1.366.736-.736 1.094-1.475 1.366-2.347.272-.872.484-2.009.542-3.29.058-1.28.072-1.688.072-4.947s-.014-3.667-.072-4.947c-.058-1.281-.27-2.418-.542-3.29-.272-.872-.63-1.611-1.366-2.347-.736-.736-1.475-1.094-2.347-1.366-.872-.272-2.009-.484-3.29-.542-1.28-.058-1.688-.072-4.947-.072zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.162 6.162 6.162 6.162-2.759 6.162-6.162-2.759-6.162-6.162-6.162zm0 10.324c-2.297 0-4.162-1.865-4.162-4.162s1.865-4.162 4.162-4.162 4.162 1.865 4.162 4.162-1.865 4.162-4.162 4.162zm6.406-11.845c-.796 0-1.441.645-1.441 1.441s.645 1.441 1.441 1.441 1.441-.645 1.441-1.441-.645-1.441-1.441-1.441z"/>
        </svg>
      </a>
    </div>
  </li>
  
  <li class="py-2 md:py-0">
    <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-500 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent">
      <a class="text-white hover:text-pink-500" href="https://github.com/tasyafbriani" target="_blank">
        <svg class="w-6 h-6" fill="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path d="M12 0c-6.627 0-12 5.373-12 12 0 5.302 3.438 9.8 8.205 11.387.6.111.82-.261.82-.579 0-.285-.011-1.04-.016-2.04-3.338.726-4.042-1.61-4.042-1.61-.546-1.387-1.333-1.756-1.333-1.756-1.089-.744.083-.729.083-.729 1.205.084 1.838 1.237 1.838 1.237 1.07 1.834 2.809 1.304 3.495.997.108-.775.418-1.304.76-1.604-2.665-.305-5.466-1.332-5.466-5.931 0-1.31.469-2.381 1.236-3.221-.124-.303-.536-1.527.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.655 1.649.243 2.873.119 3.176.77.84 1.235 1.911 1.235 3.221 0 4.61-2.804 5.624-5.475 5.921.43.371.814 1.102.814 2.222 0 1.606-.014 2.898-.014 3.293 0 .321.218.694.825.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/>
          </svg>
      </a>
    </div>
  </li>
  
  <li class="py-2 md:py-0">
    <a href="/contact">
      <div class="block px-4 py-2 rounded hover:bg-pink-400 md:hover:bg-transparent md:border-0 md:hover:text-pink-400 md:p-0 dark:hover:bg-pink-700 dark:hover:text-white md:dark:hover:bg-transparent">
        <div class="text-white bg-pink-400 hover:text-white hover:bg-pink-500 px-4 py-2 rounded" href="#">
          Let's Chat
        </div>
      </div>
    </a>
  </li>
    </ul>
  </div>
        </div>
      </nav>
    </template>
    
    <script setup>
   import { ref, onMounted, onBeforeMount, onBeforeUnmount } from "vue";
import { initDropdowns } from "flowbite";

const scrolled = ref(false);
const isMobileMenuOpen = ref(false);

const handleScroll = () => {
  scrolled.value = window.scrollY > 50;
};

const toggleMobileMenu = () => {
  isMobileMenuOpen.value = !isMobileMenuOpen.value;
};

const toggleDropdown = (id) => {
  const dropdown = document.getElementById(id);
  if (dropdown) {
    dropdown.classList.toggle('hidden');
  }
};


const scrollToSection = (sectionId) => {
  if (isMobileMenuOpen.value) {
    isMobileMenuOpen.value = false;
  }
  
  
  if (sectionId === 'home') {
    window.scrollTo({
      top: 0,
      behavior: 'smooth'
    });
    return;
  }
  
  const element = document.getElementById(sectionId);
  if (element) {
    element.scrollIntoView({
      behavior: 'smooth'
    });
  }
};

onMounted(() => {
  window.addEventListener("scroll", handleScroll);
  initDropdowns();
  
 
  document.documentElement.style.scrollBehavior = 'smooth';
  

  handleScroll();
});

onBeforeMount(() => {
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", handleScroll);
});
</script>