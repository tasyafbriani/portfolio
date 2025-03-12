
<template>
    <div>
      <Navbar />
      <div>
        <slot />
        <Footer />
      </div>
    </div>
  </template>
  
  <script>
  import Navbar from '~/components/Navbar.vue'
  
  export default {
    components: {
      Navbar
    }
  }
  </script>
  
  <style>
  @import url('https://fonts.googleapis.com/css2?family=Great+Vibes&family=Roboto:wght@400;700&display=swap');
  
  .font-roboto {
    font-family: 'Roboto', sans-serif;
  }
  </style>
  