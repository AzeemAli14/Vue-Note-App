<template>
  <teleport to="body">
    <div>
      <slot name="header" />
      <div class="text-center justify-center mx-auto flex">
        <slot />
      </div>
    </div>
  </teleport>
</template>
