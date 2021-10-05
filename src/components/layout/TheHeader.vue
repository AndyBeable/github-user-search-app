<template>
  <div class="header-container">
    <h1>devfinder</h1>
    <div class="mode-container">
      <button @click="$emit('toggle')">{{ mode }}</button>
      <img :src="moon" />
    </div>
  </div>
</template>

<script>
import moonIcon from '../../../public/assets/icon-moon.svg';

export default {
  props: ['mode'],
  data() {
    return {
      moon: moonIcon,
    };
  },
  methods: {
    toggleTheme() {},
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

.dark h1 {
  color: var(--bg-white);
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
  cursor: pointer;
}
</style>
