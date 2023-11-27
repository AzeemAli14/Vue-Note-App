<template>
    <div>
      <h1 class="font-bold text-2xl text-center my-5 underline">Modals</h1>
      <button
        @click="showModal = true"
        class="justify-center mx-auto flex py-2 px-4 bg-[#41b883] text-white rounded-xl border-4 border-[#34495e] hover:bg-green-300 hover:text-black"
      >
        Show Modal
      </button>
      <teleport to="body">
          <div v-if="showModal">
        <h1 class="font-bold text-2xl text-center my-5 underline">
          This is a Modal
        </h1>
        <p class="text-center max-w-lg my-4 bg-emerald-600 text-gray-950">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam ex
          debitis deleniti dolorem exercitationem asperiores consequuntur ipsum
          eaque nihil quidem accusamus dolore sunt dolor culpa, id tempore sit
          doloribus ut!
        </p>
        <button
        @click="showModal = false"
        class="justify-center mx-auto my-5 flex py-2 px-4 bg-[#41b883] text-white rounded-xl border-4 border-[#34495e] hover:bg-green-300 hover:text-black"
      >
        Hide Modal
      </button>
      </div>
      </teleport>
    </div>
  </template>
  
  <script setup>
  import { ref } from "vue";
  
  const showModal = ref(false);
  </script>
  