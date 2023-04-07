<template>
  <div class="grid-layout">
    <slot></slot>
  </div>
</template>

<style>
.grid-layout {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 1rem;
  padding: 1rem;
}
</style>
