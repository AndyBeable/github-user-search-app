<template>
  <div class="wrapper">
    <slot></slot>
  </div>
</template>

<style scoped>
.wrapper {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  height: 100vh;
  width: 92%;
  margin: 0 auto;
}

@media screen and (min-width: 768px) {
  .wrapper {
    width: 80%;
  }
}
</style>
