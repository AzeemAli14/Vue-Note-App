<template>
  <div class="posts">
    <h1 class="text-center text-2xl py-4 font-extrabold text-white hover:text-[#41b883] underline">
      Post
    </h1>
    <p class="text-white">
      Display the content of the post
      <span class="text-[#41b883] text-xl font-bold">{{
        $route.params.id
      }}</span>
      here!
    </p>
    <div class="my-4 flex">
    <button class="border-4 border-[#34495e] text-white px-3 py-1 bg-[#41b883] rounded-xl hover:bg-green-300 m-auto justify-center" @click="showPostId">Show Post ID</button>
    </div>
    <p>
      <RouterLink
        to="/"
        class="text-white hover:text-[#41b883] hover:bg-transparent"
        ><span class="px-2">&larr;</span>Back</RouterLink
      >
    </p>
  </div>
</template>

<script setup>
import { useRoute } from 'vue-router';

const route = useRoute();

const showPostId = () => {
  alert('The ID of this post is: ${route.params.id}');
}
</script>

<style scoped></style>
