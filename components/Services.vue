 <template>
    <section id="services">

 <div class="flex flex-col md:flex-row items-center justify-center p-8 md:p-16 min-h-screen bg-gradient-to-br from-[#E6D5C3] via-fuchsia-400 to-rose-300 ">
  <div class="container mx-auto py-12 px-4">
      <h1 class="text-4xl font-bold mb-12 text-rose-900">Why Hire Me</h1>
      <div class="flex justify-center space-x-4 mb-8">
        <div class="tabs-container relative">
  <div class="flex space-x-4 mb-4 justify-center md:justify-start">
    <button 
      ref="btnService"
      @click="setActiveTab('service')" 
      :class="['font-semibold px-4 py-2 rounded-md transition-all duration-300 mb-3 border-2', 
               selectedSection === 'service' ? 'text-rose-600 bg-rose-200 border-transparent' : 'text-rose-900 border-rose-400 hover:border-rose-600']">
      My Service
    </button>
    <button 
      ref="btnSkills"
      @click="setActiveTab('skills')" 
      :class="['font-semibold px-4 py-2 rounded-md transition-all duration-300 mb-3 border-2', 
               selectedSection === 'skills' ? 'text-rose-600 bg-rose-200 border-transparent' : 'text-rose-900 border-rose-400 hover:border-rose-600']">
      Skills
    </button>
  </div>
  <div 
    class="indicator h-1 bg-rose-800 absolute bottom-0 transition-transform duration-300 rounded-full"
    :style="{ width: indicatorWidth + 'px', transform: 'translateX(' + indicatorPosition + 'px)' }">
  </div>
</div>

        <!-- <button 
    @click="selectedSection = 'skills'" 
    :class="['py-2 px-6 rounded-lg border border-rose-500 transition-all', 
             selectedSection === 'skills' ? 'bg-rose-500 text-white' : 'bg-rose-300 text-rose-900 hover:bg-rose-500']">
    Skills
  </button>
  <button 
    @click="selectedSection = 'service'" 
    :class="['py-2 px-6 rounded-lg border border-rose-500 transition-all', 
             selectedSection === 'service' ? 'bg-rose-500 text-white' : 'bg-rose-300 text-rose-900 hover:bg-rose-500']">
    My Service
  </button> -->

  <!-- <button 
    @click="selectedSection = 'education'" 
    :class="['py-2 px-6 rounded-lg border border-rose-500 transition-all', 
             selectedSection === 'education' ? 'bg-rose-500 text-white' : 'bg-rose-300 text-rose-900 hover:bg-rose-500']">
    Education
  </button> -->
</div>


<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6" v-if="selectedSection === 'service'">
  <div class="relative p-6 border border-rose-500 rounded-lg shadow-md text-rose-900 group overflow-hidden transition-all duration-500 transform hover:scale-105 min-h-[280px] flex flex-col">
    <div class="absolute inset-0 bg-rose-500 scale-0 group-hover:scale-100 transition-transform duration-500 ease-in-out origin-center"></div>
    <h2 class="relative flex items-center space-x-2 text-lg font-semibold text-rose-900 mb-2 transition-all duration-300 group-hover:text-white">
    <img width="50" height="50" src="https://img.icons8.com/bubbles/100/this-pc.png" alt="this-pc"/>
    <span>Front End Web</span>
  </h2>
  <p class="relative text-rose-800 transition-all duration-300 group-hover:text-white text-justify">
  I create UI/UX based web designs using Tailwind CSS for styling. To consume APIs, I use Vue/Nuxt front-end framework.
</p>
  </div>
  
  <div class="relative p-6 border border-rose-500 rounded-lg shadow-md text-rose-900 group overflow-hidden transition-all duration-500 transform hover:scale-105">
    <div class="absolute inset-0 bg-rose-500 scale-0 group-hover:scale-100 transition-transform duration-500 ease-in-out origin-center"></div>
    <h2 class="relative flex items-center space-x-2 text-lg font-semibold text-rose-900 mb-2 transition-all duration-300 group-hover:text-white">
    <img width="50" height="50"  src="https://img.icons8.com/bubbles/100/code.png" alt="code"/>
    <span>Backend Development</span>
  </h2>
    <p class="relative text-rose-800 transition-all duration-300 group-hover:text-white text-justify">
      I use JavaScript as a programming language and utilize Supabase as a backend.
    </p>
  </div>

  <div class="relative p-6 border border-rose-500 rounded-lg shadow-md text-rose-900 group overflow-hidden transition-all duration-500 transform hover:scale-105">
    <div class="absolute inset-0 bg-rose-500 scale-0 group-hover:scale-100 transition-transform duration-500 ease-in-out origin-center"></div>   
  <h2 class="relative flex items-center space-x-2 text-lg font-semibold text-rose-900 mb-2 transition-all duration-300 group-hover:text-white">
    <img width="50" height="50" src="https://img.icons8.com/bubbles/100/design.png" alt="design"/>
    <span>UI/UX Design</span>
  </h2>
    <p class="relative text-rose-800 transition-all duration-300 group-hover:text-white text-justify">
      I use Figma to design user interfaces.
    </p>
  </div>
</div>

<div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5 xl:grid-cols-6 gap-6 md:gap-8" v-if="selectedSection === 'skills'">
    <div v-for="(skill, index) in skills" :key="index" 
      class="flex flex-col items-center group transition-all duration-500 hover:scale-110">

      <div class="w-24 h-24 rounded-2xl bg-white/10 border border-transparent
        flex items-center justify-center p-3 shadow-lg shadow-fuchsia-500/20 
        transition-all duration-500 group-hover:bg-gradient-to-br from-fuchsia-500 to-rose-400/80 
        group-hover:shadow-2xl group-hover:shadow-fuchsia-500/40 backdrop-blur-lg">
        
        <img :src="skill.icon" alt="Skill Icon" 
          class="w-14 h-14 object-contain transition-all duration-500 group-hover:scale-125" />
      </div>


      <p class="mt-2 text-sm font-medium text-gray-800 text-center transition-all duration-500 group-hover:text-white">
        {{ skill.name }}
      </p>
    </div>
</div>


<!-- <div class="grid grid-cols-1 md:grid-cols-3 gap-6" v-if="selectedSection === 'education'">
  <div class="relative p-6 border border-rose-200 rounded-lg shadow-md text-rose-900 group overflow-hidden transition-all duration-500 transform hover:scale-105">
    
    <div class="absolute inset-0 bg-rose-500 translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-in-out"></div>

   
    <h2 class="relative text-lg font-semibold text-rose-900 mb-2 transition-all duration-300 group-hover:text-white">
      Software Engineer
    </h2>
    <p class="relative text-sm text-rose-700 transition-all duration-300 group-hover:text-white">03/2008 – 07/2011</p>
    <p class="relative text-sm text-rose-600 transition-all duration-300 group-hover:text-white">Spotify</p>
  </div>

  <div class="relative p-6 border border-rose-200 rounded-lg shadow-md text-rose-900 group overflow-hidden transition-all duration-500 transform hover:scale-105">
    <div class="absolute inset-0 bg-rose-500 translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-in-out"></div>

    <h2 class="relative text-lg font-semibold text-rose-900 mb-2 transition-all duration-300 group-hover:text-white">
      Software Engineer
    </h2>
    <p class="relative text-sm text-rose-700 transition-all duration-300 group-hover:text-white">03/2008 – 07/2011</p>
    <p class="relative text-sm text-rose-600 transition-all duration-300 group-hover:text-white">Spotify</p>
  </div>

  <div class="relative p-6 border border-rose-200 rounded-lg shadow-md text-rose-900 group overflow-hidden transition-all duration-500 transform hover:scale-105">
    <div class="absolute inset-0 bg-rose-500 translate-x-full group-hover:translate-x-0 transition-transform duration-500 ease-in-out"></div>

    <h2 class="relative text-lg font-semibold text-rose-900 mb-2 transition-all duration-300 group-hover:text-white">
      Software Engineer
    </h2>
    <p class="relative text-sm text-rose-700 transition-all duration-300 group-hover:text-white">03/2008 – 07/2011</p>
    <p class="relative text-sm text-rose-600 transition-all duration-300 group-hover:text-white">Spotify</p>
  </div>
</div> -->

    </div>
  </div>
  </section>
</template>

<script>
export default {
  name: 'HomePage',
  data() {
    return {
      selectedSection: 'service', 
      indicatorWidth: 0,
      indicatorPosition: 0,
      skills: [
        { name: 'Vue.js', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vuejs/vuejs-original.svg' },
        { name: 'Nuxt.js', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nuxtjs/nuxtjs-original.svg' },
        { name: 'JavaScript', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg' },
        { name: 'Tailwind CSS', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/tailwindcss/tailwindcss-original.svg' },
        { name: 'Figma', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/figma/figma-original.svg' },
        { name: 'Python', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg' },
        { name: 'C#', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/csharp/csharp-original.svg' },
        { name: 'CSS', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg' },
        { name: 'HTML', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg' },
        { name: 'Bootstrap', icon: 'https://cdn.jsdelivr.net/gh/devicons/devicon/icons/bootstrap/bootstrap-original.svg' },
      ],
    };
  },
  mounted() {
    this.updateIndicator(); 
    window.addEventListener('resize', this.updateIndicator); 
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.updateIndicator);
  },
  methods: {
    setActiveTab(tab) {
      this.selectedSection = tab;
      this.updateIndicator();
    },
    updateIndicator() {
      this.$nextTick(() => {
        const activeBtn = this.selectedSection === 'service' ? this.$refs.btnService : this.$refs.btnSkills;
        if (activeBtn) {
          this.indicatorWidth = activeBtn.offsetWidth;
          this.indicatorPosition = activeBtn.offsetLeft;
        }
      });
    }
  }
};
</script>

