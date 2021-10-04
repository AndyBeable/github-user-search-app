<template>
  <div class="header-container">
    <h1>devfinder</h1>
    <div class="mode-container">
      <button>DARK</button>
      <img :src="moon" />
    </div>
  </div>
</template>

<script>
import moonIcon from '../../../public/assets/icon-moon.svg';

export default {
  data() {
    return {
      moon: moonIcon,
    };
  },
};
</script>

<style scoped>
.header-container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 80%;
}
.mode-container {
  display: flex;
  align-items: center;
}

button {
  display: flex;
  justify-content: space-between;
  color: #697c9a;
  background-color: inherit;
  border: none;
}
</style>
