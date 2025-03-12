<template>
  <section id="about">
    <div class="flex flex-col items-center justify-center p-4 md:p-12 min-h-screen bg-gradient-to-br from-[#F3E5E0] via-rose-200 to-fuchsia-200">
      <div class="max-w-4xl mx-auto p-4 md:p-8 bg-gradient-to-tr from-[#DEB887] via-rose-300 to-fuchsia-300 rounded-xl shadow-lg flex flex-col md:flex-row items-center w-full min-h-[400px]">
        <div class="w-full md:w-1/2 flex justify-center mb-6 md:mb-0">
          <div class="relative w-60 h-60 md:w-72 md:h-72 p-1 border-2 border-purple-500 rounded-full overflow-hidden hover:scale-105 transition duration-300 ">
            <img src="assets/img/tsy1.jpeg" alt="Profile" class="w-full h-full object-cover rounded-full">
          </div>
        </div>
        <div class="w-full md:w-1/2 md:pl-8 px-4">
          <h1 class="text-3xl md:text-4xl font-bold mb-4 md:mb-6 text-rose-900 drop-shadow-md text-center md:text-left">About Me</h1>
          <p class="mb-6 text-justify text-[#2C3E50] leading-relaxed">
            Hii👋, my name is <span class="text-rose-800 font-semibold ">Tasya Nur Febriani Putri</span>. 
            I am <span class="text-rose-800 font-semibold">18 years</span> old and have a high passion to develop my knowledge and skills. 
            Currently, I am studying in the <span class="text-rose-800 font-semibold">Software and Game Development</span> department. 
            I believe that commitment to continuous learning is the key to success in the ever-growing digital era.
          </p>
          <div class="tabs-container relative">
            <div class="flex space-x-4 mb-4 justify-center md:justify-start">
              <button @click="setActiveTab('Hobbies')" 
                :class="{'text-rose-600 bg-rose-200': activeTab === 'Hobbies', 'text-rose-900': activeTab !== 'Hobbies'}" 
                class="font-semibold px-4 py-2 rounded-md transition-colors duration-300 mb-3"
                ref="tabHobbies">
                Hobbies
              </button>
              <button @click="setActiveTab('Social Media')" 
                :class="{'text-rose-600 bg-rose-200': activeTab === 'Social Media', 'text-rose-900': activeTab !== 'Social Media'}" 
                class="font-semibold px-4 py-2 rounded-md transition-colors duration-300 mb-3"
                ref="tabSocial">
                Social Media
              </button>
            </div>
            <div class="indicator" ref="indicator"></div>
          </div>
          <div class="tab-content min-h-[120px] mt-2">
            <div v-if="activeTab === 'Hobbies'" class="flex justify-center md:justify-start">
              <ul class="list-none p-0">
                <li class="flex items-center mb-3 hover:scale-105 transition duration-300 ">
                  <img width="24" height="24" src="https://img.icons8.com/office/40/book.png" alt="book" class="mr-2"/>
                  <span>Reading</span>
                </li>
                <li class="flex items-center mb-3 hover:scale-105 transition duration-300 ">
                  <img width="24" height="24" src="https://img.icons8.com/emoji/48/dancing-girl.png" alt="dancing-girl" class="mr-2"/>
                  <span>Dance</span>
                </li>
                <li class="flex items-center mb-3 hover:scale-105 transition duration-300 ">
                  <img width="24" height="24" src="https://img.icons8.com/external-justicon-flat-justicon/64/external-cooking-cooking-justicon-flat-justicon.png" alt="external-cooking-cooking-justicon-flat-justicon " class="mr-2"/>
                  <span>Cooking</span>
                </li>
              </ul>
            </div>
            <div v-else-if="activeTab === 'Social Media'" class="flex justify-center md:justify-start">
              <ul class="list-none p-0 flex space-x-4 ">
                <!-- <li class="hover:scale-105 transition duration-300 ">
                  <button class="bg-blue-500 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded hover:bg-blue-600 transition-colors">
                    <svg class="w-5 h-5 fill-current" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z" /></svg>
                  </button>
                </li>
                <li class="hover:scale-105 transition duration-300 ">
                  <button class="bg-blue-400 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded hover:bg-blue-500 transition-colors">
                    <svg class="w-5 h-5 fill-current" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z" /></svg>
                  </button>
                </li>
                <li   class="hover:scale-105 transition duration-300 ">
                  <button class="bg-red-600 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded hover:bg-red-700 transition-colors">
                    <svg class="w-5 h-5 fill-current" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 16 16"><path d="M8.051 1.999h.089c.822.003 4.987.033 6.11.335a2.01 2.01 0 0 1 1.415 1.42c.101.38.172.883.22 1.402l.01.104.022.26.008.104c.065.914.073 1.77.074 1.957v.075c-.001.194-.01 1.108-.082 2.06l-.008.105-.009.104c-.05.572-.124 1.14-.235 1.558a2.007 2.007 0 0 1-1.415 1.42c-1.16.312-5.569.334-6.18.335h-.142c-.309 0-1.587-.006-2.927-.052l-.17-.006-.087-.004-.171-.007-.171-.007c-1.11-.049-2.167-.128-2.654-.26a2.007 2.007 0 0 1-1.415-1.419c-.111-.417-.185-.986-.235-1.558L.09 9.82l-.008-.104A31.4 31.4 0 0 1 0 7.68v-.123c.002-.215.01-.958.064-1.778l.007-.103.003-.052.008-.104.022-.26.01-.104c.048-.519.119-1.023.22-1.402a2.007 2.007 0 0 1 1.415-1.42c.487-.13 1.544-.21 2.654-.26l.17-.007.172-.006.086-.003.171-.007A99.788 99.788 0 0 1 7.858 2h.193zM6.4 5.209v4.818l4.157-2.408L6.4 5.209z" /></svg>
                  </button>
                </li> -->
                <li  class="hover:scale-105 transition duration-300 ">
                  <a  href="https://www.instagram.com/tsyafbrni?igsh=MTBkNDh4ZmQyb2I4YQ=="  target="_blank"
                                class="bg-gradient-to-r from-purple-500 via-pink-500 to-orange-500 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded hover:opacity-90 transition-opacity">
                                <svg class="w-5 h-5 fill-current" role="img" viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M12 0C8.74 0 8.333.015 7.053.072 5.775.132 4.905.333 4.14.63c-.789.306-1.459.717-2.126 1.384S.935 3.35.63 4.14C.333 4.905.131 5.775.072 7.053.012 8.333 0 8.74 0 12s.015 3.667.072 4.947c.06 1.277.261 2.148.558 2.913.306.788.717 1.459 1.384 2.126.667.666 1.336 1.079 2.126 1.384.766.296 1.636.499 2.913.558C8.333 23.988 8.74 24 12 24s3.667-.015 4.947-.072c1.277-.06 2.148-.262 2.913-.558.788-.306 1.459-.718 2.126-1.384.666-.667 1.079-1.335 1.384-2.126.296-.765.499-1.636.558-2.913.06-1.28.072-1.687.072-4.947s-.015-3.667-.072-4.947c-.06-1.277-.262-2.149-.558-2.913-.306-.789-.718-1.459-1.384-2.126C21.319 1.347 20.651.935 19.86.63c-.765-.297-1.636-.499-2.913-.558C15.667.012 15.26 0 12 0zm0 2.16c3.203 0 3.585.016 4.85.071 1.17.055 1.805.249 2.227.415.562.217.96.477 1.382.896.419.42.679.819.896 1.381.164.422.36 1.057.413 2.227.057 1.266.07 1.646.07 4.85s-.015 3.585-.074 4.85c-.061 1.17-.256 1.805-.421 2.227-.224.562-.479.96-.897 1.382-.419.419-.824.679-1.38.896-.42.164-1.065.36-2.235.413-1.274.057-1.649.07-4.859.07-3.211 0-3.586-.015-4.859-.074-1.171-.061-1.816-.256-2.236-.421-.569-.224-.96-.479-1.379-.897-.421-.419-.69-.824-.9-1.38-.165-.42-.359-1.065-.42-2.235-.045-1.26-.061-1.649-.061-4.844 0-3.196.016-3.586.061-4.861.061-1.17.255-1.814.42-2.234.21-.57.479-.96.9-1.381.419-.419.81-.689 1.379-.898.42-.166 1.051-.361 2.221-.421 1.275-.045 1.65-.06 4.859-.06l.045.03zm0 3.678c-3.405 0-6.162 2.76-6.162 6.162 0 3.405 2.76 6.162 6.162 6.162 3.405 0 6.162-2.76 6.162-6.162 0-3.405-2.76-6.162-6.162-6.162zM12 16c-2.21 0-4-1.79-4-4s1.79-4 4-4 4 1.79 4 4-1.79 4-4 4zm7.846-10.405c0 .795-.646 1.44-1.44 1.44-.795 0-1.44-.646-1.44-1.44 0-.794.646-1.439 1.44-1.439.793-.001 1.44.645 1.44 1.439z" />
                                </svg>
                            </a>
                            </li>
                            <li  class="hover:scale-105 transition duration-300 ">
  <a href="https://github.com/tasyafbriani"target="_blank"
                                class="bg-gray-800 p-2 font-semibold text-white inline-flex items-center space-x-2 rounded hover:bg-gray-700 transition-colors">
                                <svg class="w-5 h-5 fill-current" role="img" viewBox="0 0 24 24"
                                    xmlns="http://www.w3.org/2000/svg">
                                    <path
                                        d="M12 .297c-6.63 0-12 5.373-12 12 0 5.303 3.438 9.8 8.205 11.385.6.113.82-.258.82-.577 0-.285-.01-1.04-.015-2.04-3.338.724-4.042-1.61-4.042-1.61C4.422 18.07 3.633 17.7 3.633 17.7c-1.087-.744.084-.729.084-.729 1.205.084 1.838 1.236 1.838 1.236 1.07 1.835 2.809 1.305 3.495.998.108-.776.417-1.305.76-1.605-2.665-.3-5.466-1.332-5.466-5.93 0-1.31.465-2.38 1.235-3.22-.135-.303-.54-1.523.105-3.176 0 0 1.005-.322 3.3 1.23.96-.267 1.98-.399 3-.405 1.02.006 2.04.138 3 .405 2.28-1.552 3.285-1.23 3.285-1.23.645 1.653.24 2.873.12 3.176.765.84 1.23 1.91 1.23 3.22 0 4.61-2.805 5.625-5.475 5.92.42.36.81 1.096.81 2.22 0 1.606-.015 2.896-.015 3.286 0 .315.21.69.825.57C20.565 22.092 24 17.592 24 12.297c0-6.627-5.373-12-12-12" />
                                </svg>
                            </a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'AboutMe',
  data() {
    return {
      activeTab: 'Hobbies', 
    };
  },
  methods: {
    setActiveTab(tab) {
      console.log('Tab clicked:', tab);
      this.activeTab = tab;
      this.$nextTick(() => {
        this.updateIndicator();
      });
    },
    updateIndicator() {
      const tabRefs = {
        'Hobbies': this.$refs.tabHobbies,
        'Social Media': this.$refs.tabSocial,
      };

    
      const activeElement = tabRefs[this.activeTab];
      const indicator = this.$refs.indicator;

      if (activeElement && indicator) {
        indicator.style.width = `${activeElement.offsetWidth}px`;
        indicator.style.transform = `translateX(${activeElement.offsetLeft}px)`;
      }
    }
  },
  mounted() {
    this.$nextTick(() => {
      this.updateIndicator();
      window.addEventListener('resize', this.updateIndicator);
    });
  },
  beforeDestroy() {
    window.removeEventListener('resize', this.updateIndicator);
  }
};
</script>

<style scoped>
body {
  font-family: 'Roboto', sans-serif;
  background-color: #1a1a1a;
  color: #ffffff;
}
.tabs-container {
  position: relative;
}

.indicator {
  height: 2px;
  background-color: theme('colors.rose.800');
  position: absolute;
  bottom: 0;
  transition: transform 0.3s ease, width 0.3s ease;
}
</style>