<template>
    <div class="flex flex-col md:flex-row items-center justify-center p-8 md:p-16 min-h-screen bg-gradient-to-br from-[#E6D5C3] via-fuchsia-400 to-rose-300 ">
        <div class="text-center md:text-left md:w-1/2">
            <h1 class="text-4xl md:text-5xl font-bold mb-4 text-slate-800 drop-shadow-md">
    Hi, I'm
    <span class="text-slate-800 drop-shadow-md">
        tsyafbriani
    </span>
</h1>

<div class="text-3xl md:text-3xl text-gray-700 drop-shadow-md">
        <h2> I'm a <span class="typewriter font-semibold  drop-shadow-[2px_2px_4px_rgba(255,255,255,1)] drop-shadow-[4px_4px_8px_rgba(255,255,255,0.6)]">Software Engineer</span></h2>
      </div>
        </div>

<div class="mt-8 md:mt-0 md:w-1/2 flex justify-center items-center">
    <img
      alt="A cute white cat with a curious expression"
      class="home-img-img"
      src="assets/img/p.jpg"
    />
</div>
    </div>
</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&display=swap');

.home-img-img {
  position: relative;
  top: 3rem;
  width: 25vw;
  aspect-ratio: 1/1;  
  border-radius: 50%;
  border: 4px solid rgb(245, 79, 162); 
  object-fit: cover;
  box-shadow: 0 0 15px rgba(245, 79, 162, 0.8); 
  cursor: pointer;
  transition: box-shadow 0.4s ease-in-out, transform 0.3s ease-in-out;
}

.home-img-img:hover {
  box-shadow: 
    0 0 35px rgba(230, 50, 150, 0.9),  
    0 0 70px rgba(170, 70, 200, 1),     
    0 0 100px rgba(140, 60, 180, 1);   
  transform: scale(1.07); 
  transition: box-shadow 0.3s ease-in-out, transform 0.3s ease-in-out;
}


.typewriter {
  color: #9333ea; 
  font-family: 'Poppins', sans-serif;
  font-weight: 600;
  display: inline-block;
  overflow: hidden;
  border-right: 0.15em solid rgb(145, 23, 150);
  white-space: nowrap;
  letter-spacing: 0.15em;
  animation: 
    ttyping 8s steps(50) forwards, 
    blink-caret 1s step-end infinite; 
  vertical-align: top;
  width: 0;
}

@keyframes ttyping {
  from { width: 0 }
  to { width: 360px } 
}

@keyframes blink-caret {
  from, to { border-color: transparent }
  50% { border-color: rgb(178, 64, 182) }
}


@media (max-width: 768px) {
  .home-img-img {
    width: 50vw;
    top: 2rem;
  }

  .typewriter {
    font-size: 1.5rem;
  }

  h1 {
    font-size: 2.5rem;
  }

  h2 {
    font-size: 2rem;
    font-family: 'Inter', sans-serif;
    
  }
}
</style>