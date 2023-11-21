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
    <p>
      <RouterLink
        to="/"
        class="text-white hover:text-[#41b883] hover:bg-transparent"
        ><span class="px-2">&larr;</span>Back</RouterLink
      >
    </p>
  </div>
</template>

<script setup></script>

<style scoped></style>
