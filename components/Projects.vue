 <template>
      <section id="projects" class="flex flex-col items-center justify-center p-8 md:p-16 min-h-screen 
       bg-gradient-to-br from-[#F3E5E0] via-rose-200 to-fuchsia-200   w-full">
        
       <div class="mb-5 text-center">
      <h1 class="text-3xl md:text-4xl font-bold mt-2">
        My <span class="font-bold mb-12 text-rose-900"> Projects</span>
      </h1>
    </div>
       <div class="w-full min-h-[400px] flex flex-col items-center justify-center mt-5">
  <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 px-4 md:px-8 lg:px-16">
    <div v-for="project in projects" :key="project.id" class="bg-white/70 backdrop-blur-sm shadow-xl p-4 rounded-lg text-left 
         transition duration-300 hover:bg-white/80 h-full flex flex-col">
      <div class="overflow-hidden rounded-lg mb-4">
        <img 
          :src="project.image" 
          :alt="project.alt" 
          class="w-full h-48 object-cover rounded-lg transform hover:scale-105 transition duration-300 " 
        />
      </div>
      <p class="text-gray-600 text-sm">{{ project.category }}</p>
      <h5 class="text-lg md:text-xl font-bold mt-1 text-rose-900">{{ project.name }}</h5>
      <p class="mt-4 text-purple-900 text-xs md:text-sm leading-relaxed">
  {{ project.description || 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' }}
</p>

      <div class="mt-3 flex justify-end items-center">

  <a 
    class="size-10 inline-flex justify-center items-center gap-x-2 text-sm font-semibold rounded-full border border-transparent text-gray-700 hover:text-black hover:bg-gray-300 focus:outline-none focus:bg-gray-300" 
    href="https://github.com/tasyafbriani" 
    target="_blank"
  >
    <svg class="shrink-0 size-6" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 16">
      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
    </svg>
  </a>
</div>

    </div>
  </div>
</div> 
        
        <nuxt-link to="/projects" class="flex items-center bg-fuchsia-500 text-white border border-fuchsia-500 rounded-full p-1 hover:bg-transparent hover:text-fuchsia-600 transition mt-10">
  <div class="bg-pink-300 text-white border border-fuchsia-500 rounded-full p-2 hover:bg-transparent hover:text-fuchsia-600">
    <img width="24" height="24" src="https://img.icons8.com/material-outlined/24/circled-right.png" alt="circled-right"/>
  </div>
  <div class="px-4 py-2 ml-2">
    View All Projects
  </div>
</nuxt-link>
      </section>
    </template>
    
    <script>
    import image from '/assets/img/project/tefa.png';
    import image1 from '/assets/img/project/game.png';
    import image2 from '/assets/img/project/web.png'
    
    export default {
      name: 'Portfolio',
      data() {
        return {
          projects: [
            {
              id: 1,
              image: image, 
              alt: 'Perpus',
              name: 'Pepustakaan Digital',
              category: 'Web Development',
              description: 'Library website with digital notebook to record name and purpose of visit, as well as search and borrow books.',
              
            },
            {
              id: 2,
              image: image1, 
              alt: 'game ar',
              name: 'Game Card',
              category: 'Game',
              description: 'A mobile card game with beautiful graphics and engaging gameplay, where players match names to photos of food.',
            },
            {
              id: 3,
              image: image2, 
              alt: 'web smk4',
              name: 'Website SMKN4',
              category: 'Web Development',
              description: 'A school website that provides comprehensive information about the school for the school community and the public.',
            },
          ]
        };
      }
    };
    </script>
        
<style scoped>
body {
  font-family: 'Roboto', sans-serif;
}
</style>
