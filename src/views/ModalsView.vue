<template>
  <div>
    <h1 class="font-bold text-2xl text-center my-5 underline">Modals</h1>
    <button
      @click="showModal = !showModal"
      class="justify-center mx-auto flex py-2 px-4 rounded-xl border-4
      bg-[#41b883] 
      text-white 
      border-[#34495e] 
      hover:bg-green-300 
      hover:text-black
      active:border-[#41b883]
      active:text-white
      active:bg-[#34495e]"
    >
      Show/Hide Modal
    </button>
    <Modal v-if="showModal">
      <template v-slot:header>
        <h1 class="font-bold text-2xl text-center my-5 underline">
          Modal Header
        </h1>
      </template>
      <p class="text-center max-w-lg my-4 bg-emerald-600 text-gray-950">
        Lorem ipsum dolor sit amet consectetur adipisicing elit. Aperiam ex
        debitis deleniti dolorem exercitationem asperiores consequuntur ipsum
        eaque nihil quidem accusamus dolore sunt dolor culpa, id tempore sit
        doloribus ut!
      </p>
    </Modal>
  </div>
</template>

<script setup>
import Modal from "@/components/modals/teleportModal.vue";
import { ref } from "vue";

const showModal = ref(false);
</script>
