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
  /* height: 70rem; */
  width: 80%;
  margin: 0 auto;
}
</style>
