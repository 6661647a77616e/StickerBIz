<!-- <script setup>

</script>


<template>
    <h1>kereta sewa</h1>

    <div class="grid grid-cols-5 divide-x">

        
        <div >
            <p>PRINTING</p>
            <img
              src="C:\Users\User\OneDrive\Pictures\website\WhatsApp Image 2023-12-17 at 19.03.59_1a1e275d.jpg"
              height="200"
              width="200"
              class="mx-auto flex items-center justify-center flex-col"

    
             />
        <div class="p-7">
             <p>  🖨PRINTING SERVICE🖨

            Black & White - RM0.20/page 
             Colour - RM0.50/page
             A4/A5 size paper available 

             WhatsApp
             http://wa.me/60147125241
            📍Mahallah Asiah Block F 2.7
          </p>
        </div>   
      
      </div>

      <div>02</div>
      <div>03</div>
      <div>04</div>
      <div>05</div>
     
    </div>
  
</template> -->


<template>
  <div class="min-h-screen bg-gradient-to-br from-blue-100 to-pink-100">
    <h1 class="text-4xl font-bold text-center py-6 text-pink-500 animate-bounce">
      Adventure Time Gallery!
    </h1>
    
    <div class="flex flex-wrap max-w-3xl mx-auto">
      <div v-for="(item, index) in items" 
           :key="index" 
           class="flex-shrink-0 w-full sm:w-1/2 md:w-1/3 lg:w-1/4 xl:w-1/4 p-2"
           @click="openModal(item)">
        <div class="bg-pink-300 grid grid-cols-1 rounded-2xl divide-y transform transition-all duration-300 hover:scale-105 hover:shadow-xl cursor-pointer hover:bg-pink-400">
          <div class="flex items-center justify-center p-2">
            <img :src="item.image" 
                 :alt="item.title" 
                 height="150" 
                 width="150" 
                 class="origin-center transition-all duration-300 rounded-xl hover:scale-110">
          </div>
          <div class="p-4 text-center">
            <h3 class="text-lg font-bold text-purple-800">{{ item.title }}</h3>
            <p class="text-purple-600">{{ item.description }}</p>
          </div>
        </div>
      </div>
    </div>

    <!-- Modal -->
    <div v-if="selectedItem" 
         class="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center z-50"
         @click="closeModal">
      <div class="bg-white rounded-3xl p-6 max-w-lg w-full mx-4 transform transition-all"
           @click.stop>
        <div class="flex flex-col items-center">
          <img :src="selectedItem.image" 
               :alt="selectedItem.title"
               class="w-64 h-64 object-contain mb-4 rounded-xl">
          <h2 class="text-2xl font-bold text-purple-800 mb-2">{{ selectedItem.title }}</h2>
          <p class="text-purple-600 mb-4">{{ selectedItem.description }}</p>
          <div class="text-sm text-gray-600 mb-4">{{ selectedItem.details }}</div>
          
          <button @click="closeModal"
                  class="bg-pink-500 text-white px-6 py-2 rounded-full hover:bg-pink-600 transform transition-all duration-300 hover:scale-105">
            Close
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';

const selectedItem = ref(null);

const items = [
  {
    title: "Finn",
    description: "Adventure Time",
    image: "src\\assets\\img\\Stickerz\\Finn.jpg",
    details: "Finn the Human is a brave adventurer and hero of Ooo!"
  },
  {
    title: "Jake",
    description: "Adventure time",
    image: "src\\assets\\img\\Stickerz\\Jake.jpg",
    details: "Jake the Dog can stretch into any shape and is Finn's best friend and adoptive brother."
  },
  {
    title: "Peppermint Butler",
    description: "Adventure time",
    image: "src\\assets\\img\\Stickerz\\PeppermintButler.jpg",
    details: "Princess Bubblegum's mysterious butler with dark magical powers..."
  },
  {
    title: "Lemongrab",
    description: "Adventure time",
    image: "src\\assets\\img\\Stickerz\\Lemongrab.jpg",
    details: "UNACCEPTABLE!!! (But actually pretty interesting character)"
  },
  {
    title: "BMO",
    description: "Adventure Time",
    image: "src\\assets\\img\\Stickerz\\BMO.jpg",
    details: "A living video game console and one of Finn and Jake's best friends!"
  },
  {
    title: "Princess Bubblegum",
    description: "Adventure Time",
    image: "src\\assets\\img\\Stickerz\\PB.jpg",
    details: "The scientific ruler of the Candy Kingdom and a brilliant inventor."
  },
  {
    title: "Marceline",
    description: "Adventure Time",
    image: "src\\assets\\img\\Stickerz\\Marceline.jpg",
    details: "The Vampire Queen, over 1000 years old and an amazing musician!"
  },
  {
    title: "Lady Rainicorn",
    description: "Adventure Time",
    image: "src\\assets\\img\\Stickerz\\LadyRainicorn.jpg",
    details: "Jake's girlfriend who can fly and phase through matter. Speaks Korean!"
  }
];

const openModal = (item) => {
  selectedItem.value = item;
  // Add a class to prevent scrolling when modal is open
  document.body.style.overflow = 'hidden';
};

const closeModal = () => {
  selectedItem.value = null;
  // Remove the class when modal is closed
  document.body.style.overflow = 'auto';
};
</script>

<style scoped>
.hover\:scale-120:hover {
  transform: scale(1.2);
}

/* Optional: Add some animation to the modal */
@keyframes modalPop {
  0% { transform: scale(0.9); opacity: 0; }
  100% { transform: scale(1); opacity: 1; }
}

.modal-content {
  animation: modalPop 0.3s ease-out forwards;
}
</style>