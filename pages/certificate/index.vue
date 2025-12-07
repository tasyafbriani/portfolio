<template>
   <section class="flex flex-col items-center justify-center p-4 md:p-8 lg:p-16 min-h-screen 
    bg-gradient-to-t from-rose-200 to-pink-100 hover:bg-gradient-to-b hover:from-pink-100 hover:to-rose-200 
    transition-all duration-500 ">
    
    <!-- Header -->
   <div class="mb-10 flex items-center mt-14">
  <h1 class="text-3xl md:text-4xl font-bold text-center flex-1">
    My <span class="font-bold text-rose-900">Certificate</span>
  </h1>
</div>

    <!-- Certificates Grid -->
    <div class="w-full max-w-7xl">
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-8 px-4">
        <div v-for="certificate in certificates" :key="certificate.id" 
             class="group cursor-pointer transition-all duration-500 transform hover:scale-105"
             @click="openModal(certificate)">
          <div class="relative overflow-hidden rounded-2xl shadow-xl shadow-rose-500/20 
                     transition-all duration-500 group-hover:shadow-2xl group-hover:shadow-rose-500/40">
            
            <img :src="certificate.image" :alt="certificate.title" 
                 class="w-full h-64 object-cover transition-all duration-500 group-hover:scale-110" />
            
            <div class="absolute inset-0 bg-gradient-to-t from-rose-900/80 via-transparent to-transparent 
                       opacity-0 group-hover:opacity-100 transition-opacity duration-500"></div>
            
            <div class="absolute bottom-0 left-0 right-0 p-4 transform translate-y-full 
                       group-hover:translate-y-0 transition-transform duration-500">
              <h3 class="text-white font-semibold text-lg mb-1">{{ certificate.title }}</h3>
              <p class="text-rose-200 text-sm">{{ certificate.issuer }}</p>
              <p class="text-rose-300 text-xs mt-1">{{ certificate.year }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal Certificate Popup -->
    <div v-if="showModal" 
         class="fixed inset-0  backdrop-blur-sm z-50 flex items-center justify-center p-4"
         @click="closeModal">
      <div class="relative max-w-2xl max-h-[80vh] w-full" @click.stop>
        
        <!-- Certificate Image Medium View -->
        <div class="bg-white rounded-lg shadow-2xl overflow-hidden">
          <img :src="selectedCertificate?.image" 
               :alt="selectedCertificate?.title"
               class="w-full h-auto max-h-[70vh] object-contain">
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import image from '/assets/img/sertifikat/1.jpg';
import image1 from '/assets/img/sertifikat/2.jpg';
import image2 from '/assets/img/sertifikat/3.jpg';
import image3 from '/assets/img/sertifikat/4.jpg';
import image4 from '/assets/img/sertifikat/5.jpg';
import image5 from '/assets/img/sertifikat/6.jpg';
import image6 from '/assets/img/sertifikat/7.jpg';
import image7 from '/assets/img/sertifikat/8.jpg';
import image8 from '/assets/img/sertifikat/9.jpg';
import image9 from '/assets/img/sertifikat/10.jpg';



export default {
  name: 'CertificatesGallery',
  data() {
    return {
      showModal: false,
      selectedCertificate: null,
      certificates: [
        {
          id: 1,
          image: image,
          title: 'Financial Literacy 101',
          issuer: 'Dicoding Indonesia',
          year: '2025'
        },
        {
          id: 2,
          image: image1,
          title: 'Belajar Dasar Pemrograman Web',
          issuer: 'Dicoding Indonesia',
          year: '2025'
        },
        {
          id: 3,
          image: image2,
          title: 'Belajar Dasar Pemrograman JavaScript',
          issuer: 'Dicoding Indonesia',
          year: '2025'
        },
        {
          id: 4,
          image: image3,
          title: 'Belajar Membuat Front-End Web untuk Pemula',
          issuer: 'Dicoding Indonesia',
          year: '2025'
        },
          {
          id: 5,
          image: image4,
          title: 'Belajar Dasar Manajemen Proyek',
          issuer: 'Dicoding Indonesia',
          year: '2025'
        },
        {
          id: 6,
          image: image5,
          title: 'Penghargaan atas kontribusi dan partisipasi dalam proyek IT',
          issuer: 'Astacode',
          year: '2025',
        },
        {
          id: 7,
          image: image6,
          title: 'Codejam( )',
          issuer: 'SMKN 4 Tasikmalaya',
          year: '2023'
        },
        {
          id: 8,
          image: image7,
          title: 'Penghargaan',
          issuer: 'SMKN 4 Tasikmalaya',
          year: '2022'
        },
        {
          id: 9,
          image: image8,
          title: 'Penghargaan',
          issuer: 'SMKN 4 Tasikmalaya',
          year: '2023'
        },
        {
          id: 10,
          image: image9,
          title: 'Social Emonitional Learning (SEL)',
          issuer: 'Save The Children Indonesia',
          year: '2024'
        },
      ]
    };
  },
  methods: {
    openModal(certificate) {
      this.selectedCertificate = certificate;
      this.showModal = true;
      document.body.style.overflow = 'hidden';
    },
    closeModal() {
      this.showModal = false;
      this.selectedCertificate = null;
      document.body.style.overflow = 'auto';
    }
  },
  mounted() {
    document.addEventListener('keydown', (e) => {
      if (e.key === 'Escape' && this.showModal) {
        this.closeModal();
      }
    });
  },
  beforeUnmount() {
    document.removeEventListener('keydown', this.closeModal);
    document.body.style.overflow = 'auto';
  }
};
</script>