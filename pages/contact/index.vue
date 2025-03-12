<script setup>
useHead({
  title: "Contact Us",
  meta: [
    {
      name: "description",
      content: "Contact Us Page",
    },
  ],
});
</script>

<template>
  <section id="contact">
    
    <div class="flex flex-col items-center justify-center p-6 md:p-12 min-h-screen 
      bg-gradient-to-br from-[#E6D5C3] via-fuchsia-400 to-rose-300 ">
      <div class="w-full max-w-2xl bg-white bg-opacity-30 p-10 rounded-lg shadow-lg 
        backdrop-blur-md border border-white/20" 
        data-aos="fade-up" data-aos-duration="1000" data-aos-delay="200 " >
        <div class=" mt-4">
              <a class="text-white font-bold flex  space-x-2 justify-start hover:text-pink-600 transition-colors duration-300" href="/">
                <img width="20" height="20" src="https://img.icons8.com/flat-round/64/left--v1.png" alt="left--v1"/>
                <span>Back</span>
              </a>
            </div>
        <h2 class="text-2xl font-semibold mb-4 text-center text-white">
          Contact <span class="text-fuchsia-600">Me</span>
        </h2>
        <hr class="border-t border-fuchsia-500 w-20 mx-auto mb-6" />

        <form class="space-y-4">
          <div class="flex flex-col md:flex-row md:space-x-4 space-y-4 md:space-y-0">
            <div class="w-full">
              <label for="name" class="text-white block mb-1">Name</label>
              <input 
                type="text" 
                id="name"
                class="p-3 w-full border border-fuchsia-500 rounded-lg text-base bg-white bg-opacity-20 
                  focus:outline-none focus:border-white placeholder-white/70 text-white"
                placeholder="Enter your name"
              />
            </div>
            <div class="w-full">
              <label for="email" class="text-white block mb-1">Email</label>
              <input 
                type="email" 
                id="email"
                class="p-3 w-full border border-fuchsia-500 rounded-lg text-base bg-white bg-opacity-20 
                  focus:outline-none focus:border-white placeholder-white/70 text-white"
                placeholder="Enter your email"
              />
            </div>
          </div>

        

          <div>
            <label for="message" class="text-white block mb-1">Your Message</label>
            <textarea 
              id="message"
              rows="4"
              class="p-3 w-full border border-fuchsia-500 rounded-lg text-base bg-white bg-opacity-20 
                focus:outline-none focus:border-white placeholder-white/70 text-white"
              placeholder="Type your message here"
            ></textarea>
          </div>

          <div class="flex justify-center">
            <button 
              type="submit"
              class="bg-fuchsia-600 text-white py-3 px-8 rounded-lg hover:bg-rose-500 
                focus:outline-none focus:ring-2 focus:ring-white focus:ring-offset-2 
                transition-transform duration-300 transform hover:scale-105 mt-2 text-base">
              Submit
            </button>
          </div>
        </form>
      </div>
    </div>
  </section>
</template>

<style scoped>
body {
  font-family: 'Roboto', sans-serif;
  background-color: #1a1a1a;
  color: #ffffff;
}
</style>
