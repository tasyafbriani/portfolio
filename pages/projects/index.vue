<template>
  <section class="flex flex-col items-center justify-center p-4 md:p-8 lg:p-16 min-h-screen 
    bg-gradient-to-t from-rose-200 to-pink-100 hover:bg-gradient-to-b hover:from-pink-100 hover:to-rose-200 
    transition-all duration-500 "> 
    <div class="mb-10 flex items-center mt-14">
  <h1 class="text-3xl md:text-4xl font-bold text-center flex-1">
    My <span class="font-bold text-rose-900">Latest Projects</span>
  </h1>
</div>

    
     <div class="flex flex-wrap justify-center gap-4 md:gap-8 mb-8 md:mb-12 w-full max-w-4xl">
      <button @click="filterProjects('All')" 
        :class="{'text-rose-600 border-b-2 border-white font-medium': selectedCategory === 'All', 
                'text-gray-400 hover:text-gray-200': selectedCategory !== 'All'}"
        class="px-3 py-1 transition duration-300">
        All
      </button>
      <button @click="filterProjects('Game')" 
        :class="{'text-rose-600 border-b-2 border-white font-medium': selectedCategory === 'Game', 
                'text-gray-400 hover:text-gray-200': selectedCategory !== 'Game'}"
        class="px-3 py-1 transition duration-300">
        Game
      </button>
      <button @click="filterProjects('Web Development')" 
        :class="{'text-rose-600 border-b-2 border-white font-medium': selectedCategory === 'Web Development', 
                'text-gray-400 hover:text-gray-200': selectedCategory !== 'Web Development'}"
        class="px-3 py-1 transition duration-300">
        Web Development
      </button>
    </div> 

    <div class="w-full max-w-6xl">

  <!-- all -->
<template v-if="selectedCategory === 'All'">
  <div
    v-for="project in projects"
    :key="project.id"
    class="mb-8 p-6 md:p-8 rounded-2xl flex flex-col lg:flex-row items-center lg:items-start 
           bg-white/20 backdrop-blur-xl shadow-xl transition duration-300 
           hover:bg-white/30 hover:scale-[1.02]"
  >
    <div class="w-full lg:w-1/2 overflow-hidden rounded-2xl">
      <img
        :alt="project.alt"
        class="w-full h-auto rounded-2xl object-cover shadow-lg transition-transform duration-500 hover:scale-105"
        :src="project.image"
      />
    </div>
    <div class="w-full lg:w-1/2 lg:pl-8 xl:pl-10 mt-6 lg:mt-0">
      <div class="flex justify-end items-center gap-2 text-gray-600 text-sm mb-2">
    <a 
      href="https://github.com/tasyafbriani" 
      target="_blank" 
      class="flex items-center gap-1 hover:text-black transition-all"
    >
      <svg class="size-5" xmlns="http://www.w3.org/2000/svg" fill="currentColor" viewBox="0 0 16 16">
        <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27.68 0 1.36.09 2 .27 1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.012 8.012 0 0 0 16 8c0-4.42-3.58-8-8-8z"/>
      </svg>
      
    </a>
  </div>
      <h2 class="text-2xl md:text-3xl font-extrabold text-purple-800">{{ project.name }}</h2>

      <div v-if="selectedCategory === 'All'" class="flex items-center justify-between pt-4 border-t border-white/10"> 
        <div class="flex flex-wrap justify-start gap-2 mb-4">
          <span 
            v-for="tech in project.tech" 
            :key="tech"
            class="px-2 md:px-3 py-1 text-xs rounded-full bg-white/20 text-gray-600 hover:bg-white/30 transition-colors"
          >
            {{ tech }}
          </span>
        </div>
      </div>

      <p class="mt-4 text-purple-900 text-base md:text-lg leading-relaxed">
        {{ project.description || 'Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.' }}
      </p>
<div class="mt-6 flex justify-end gap-4">
  <a 
    :href="project.url" 
    target="_blank"
    class="px-6 py-2.5 text-sm md:text-base rounded-full bg-gradient-to-r from-purple-600 to-purple-800 text-white 
           shadow-md hover:scale-105 transition-all duration-300"
  >
    🌍 Visit Project
  </a>
</div>
</div>
  </div>
</template>


      <!--  Game or Web Development is selected, use regular cards -->
      <div v-else class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 px-4 md:px-8 lg:px-16">
        <div v-for="project in filteredProjects" :key="project.id" class="col-span-1">
          <div class="bg-white/70 backdrop-blur-sm shadow-xl p-4 rounded-lg text-left 
                     transition duration-300  h-full flex flex-col">
            <div class="overflow-hidden rounded-lg mb-4">
              <img 
                :src="project.image" 
                :alt="project.alt" 
                class="w-full h-48 object-cover rounded-lg transform transition duration-300 hover:scale-110" 
              />
            </div>
            <p class="text-gray-600 text-sm">{{ project.category }}</p>
            <h3 class="text-lg md:text-xl font-bold mt-1">{{ project.name }}</h3>
            <p class="text-gray-700 text-sm mt-2 flex-grow">{{ project.description }}</p>
            
            <div class="mt-3 flex justify-end items-center">
  <a 
    :href="project.url" 
    target="_blank" 
    class="size-10 inline-flex justify-center items-center gap-x-2 text-sm font-semibold rounded-full border border-fuchsia-500 text-fuchsia-600 bg-fuchsia-500 hover:bg-transparent hover:text-fuchsia-600 transition transform hover:scale-110 focus:scale-110"
  >
  <svg class="shrink-0 size-6"  xmlns="http://www.w3.org/2000/svg" x="0px" y="0px" width="100" height="100" viewBox="0 0 40 40">
<path fill="#c2e8ff" d="M1.5 5.5H34.5V38.5H1.5z"></path><path fill="#7496c4" d="M34,6v32H2V6H34 M35,5H1v34h34V5L35,5z"></path><path fill="#c2e8ff" d="M30.611 13.611H37.055V15.944H30.611z" transform="rotate(90 33.833 14.778)"></path><path fill="#c2e8ff" d="M22 5H28.444V7.333H22z"></path><g><path fill="#8bb7f0" d="M18.707 16L28.707 6 24.207 1.5 38.5 1.5 38.5 15.793 34 11.293 24 21.293z"></path><path fill="#4e7ab5" d="M38,2v12.586l-3.293-3.293L34,10.586l-0.707,0.707L24,20.586L19.414,16l9.293-9.293L29.414,6 l-0.707-0.707L25.414,2H38 M39,1H23l5,5L18,16l6,6l10-10l5,5V1L39,1z"></path></g>
</svg>
  </a>

  
</div>

          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
useHead({
  title: "Projects-tasya",
  meta: [
    {
      name: "description",
      content: "Projects Page",
    },
  ],
});

  import image from '/assets/img/project/tefa.png';
    import image1 from '/assets/img/project/game.png';
    import image2 from '/assets/img/project/web.png';
    import image3 from '/assets/img/project/spw.png';
    import image5 from '/assets/img/project/quiz1.jpeg';
    import image4 from '/assets/img/project/ar.jpeg';
    import image6 from '/assets/img/project/lpk.png';
    import image7 from '/assets/img/project/asirindo.png';
    import image8 from '/assets/img/project/koyasai.png';
    import image9 from '/assets/img/project/jeep.png';
    import image10 from '/assets/img/project/daily.png';
    import image11 from '/assets/img/project/garden.png';
    import image12 from '/assets/img/project/papan.png';



export default {
  name: 'Portfolio',
  data() {
    return {
      selectedCategory: 'All',
      projects: [
        {
          id: 1,
              image: image, 
              alt: 'perpus',
              name: 'Pepustakaan Digital',
              category: 'Web Development',
              description: 'Library website with digital notebook to record name and purpose of visit, as well as search and borrow books.',
          url: 'https://tefa-ptgm.vercel.app/',
          tech: ['Vue.js', 'Nuxt.js', 'Bootstrap','PotsgreSQL'],  
        },
        {
          id: 2,
              image: image1, 
              alt: 'game card',
              name: 'Game Card',
              category: 'Game',
              description: 'A mobile card game with beautiful graphics and engaging gameplay, where players match names to photos of food.',
          url: 'https://tasyafbriani.itch.io/food-game',
          tech: ['Unity', 'C#'],  
        },
        {
id: 3,
              image: image2, 
              alt: 'web smkn4',
              name: 'Website SMKN4',
              category: 'Web Development',
              description: 'A school website that provides comprehensive information about the school for the school community and the public.',
          url: 'https://websmkn4.vercel.app/',
          tech: ['Nuxt.js', 'Vue.js', 'Bootstrap'],  
        },
        {
          id: 4,
              image: image5, 
              alt: 'quiz game',
              name: 'Game Quiz',
              category: 'Game',
              description: 'An interactive quiz game where players guess the name of an animal based on given clues.',
          url: 'https://github.com/tasyafbriani',
          tech: ['Unity', 'C#' ,'2D'],  
        },
        {
          id: 5,
              image: image4, 
              alt: 'game ar',
              name: 'Game Ar',
              category: 'Game',
              description: 'An AR game where dinosaurs appear when the camera detects a predetermined image, providing an interactive and fun experience.',
          url: 'https://github.com/tasyafbriani',
          tech: ['Unity', 'C#', '3D'],  
        },
        {
id: 6,
              image: image3, 
              alt: 'spw',
              name: 'SPW Canteen',
              category: 'Web Development',
              description: 'SPW canteen website to record student transactions and display the duty schedules of teachers and students on duty in the canteen.',
          url: 'https://spw-canteen.vercel.app/',
          tech: ['Nuxt.js', 'Vue.js', 'Bootstrap','PotsgreSQL' ],  
        },
        {
id: 7,
              image: image6, 
              alt: 'lpk',
              name: 'LPK TSUKUBA',
              category: 'Web Development',
              description: 'LPK Tsukuba website, which contains information about training programs, language courses, and job opportunities in Japan.',
          url: 'https://lpk-tsukuba.vercel.app/',
          tech: ['Nuxt.js', 'Vue.js', 'PHP Laravel','Tailwind CSS' ],  
        },
        {
id: 8,
              image: image7, 
              alt: 'asirindo',
              name: 'Asirindo',
              category: 'Web Development',
              description: 'The official website of Asirindo, a music licensing organization that collaborates with the ASTACODE team to provide copyright management and music distribution services.',
          url: 'https://asirindo.org/',
          tech: ['Nuxt.js', 'Vue.js','Tailwind CSS' ],  
        },
         {
id: 9,
              image: image8, 
              alt: 'koyasai',
              name: 'Koyasai',
              category: 'Web Development',
              description: 'Koyasai official website, a company profile created together with the ASTACODE team, provides information on fresh vegetable and fruit sales, product catalogs, and wholesale distribution services.',
          url: 'https://koyasai.co.id/',
          tech: ['Nuxt.js', 'Vue.js','Tailwind CSS','PHP Laravel'],  
        },
        {
id: 10,
              image: image9, 
              alt: 'jeep',
              name: 'Jeep Merapi',
              category: 'Web Development',
              description: 'Jeep app UI/UX, an online jeep booking platform designed in collaboration with the ASTACODE team to provide an easy, fast and informative user experience.',
          url: 'https://github.com/astacode-pkl',
          tech: ['Figma', 'UI/UX Design'],  
        },
        {
id: 11,
              image: image10, 
              alt: 'daily',
              name: 'Daily Activity',
              category: 'Web Development',
              description: 'Daily Activity Website is a web-based application designed to help users record, organize, and monitor daily activities. Equipped with activity categories and daily motivational words to increase enthusiasm and productivity.',
          url: 'https://daily-tsya.vercel.app/',
          tech: ['Nuxt.js', 'Vue.js','Tailwind CSS' ],
        },
        {
id: 12,
              image: image11, 
              alt: 'garden',
              name: 'Game Garden Grow',
              category: 'Game',
              description: 'Garden Grow is an environmentally themed game that invites players to plant, fertilize, and water plants while learning the importance of going green in a fun way.',
          url: 'https://garden-grow-two.vercel.app/',
          tech: ['Web game'],  
        },
         {
id: 13,
              image: image12, 
              alt: 'papan',
              name: 'Papan Construction',
              category: 'Web Development',
              description: 'This website is a CRM portal of the main ERP system of Papan Construction .',
          url: 'https://github.com/astacode-pkl',
          tech: ['HTML', 'Bootstrap' ],
        },
      ]
    };
  },
  computed: {
    filteredProjects() {
      if (this.selectedCategory === 'All') {
        return this.projects;
      }
      return this.projects.filter(project => project.category === this.selectedCategory);
    }
  },
  methods: {
    filterProjects(category) {
      this.selectedCategory = category;
    }
  }
};
</script>



