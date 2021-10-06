<template>
  <div class="header-container">
    <h1>devfinder</h1>
    <div class="mode-container">
      <button @click="$emit('toggleMode')">
        {{ isDark ? 'LIGHT' : 'DARK' }}
        <img v-if="isDark" :src="sun" />
        <img v-else :src="moon" />
      </button>
    </div>
  </div>
</template>

<script>
import moonIcon from '../../../public/assets/icon-moon.svg';
import sunIcon from '../../../public/assets/icon-sun.svg';
export default {
  props: ['isDark'],
  data() {
    return {
      moon: moonIcon,
      sun: sunIcon,
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

h1 {
  color: var(--heading-color);
}

.mode-container {
  display: flex;
  align-items: center;
}

button {
  display: flex;
  justify-content: space-between;
  color: var(--text-color);
  background-color: inherit;
  border: none;
  cursor: pointer;
}

button img {
  margin-left: 5px;
}
</style>
