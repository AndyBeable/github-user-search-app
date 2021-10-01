<template>
  <wrapper>
    <the-header></the-header>
    <search-bar></search-bar>
    <user-card></user-card>
  </wrapper>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import Wrapper from './components/layout/Wrapper.vue';
import SearchBar from './components/ui/SearchBar.vue';
import UserCard from './components/ui/UserCard.vue';

export default {
  name: 'App',
  components: {
    TheHeader,
    Wrapper,
    SearchBar,
    UserCard,
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap');

* {
  box-sizing: border-box;
}

html {
  font-family: 'Space Mono', monospace, sans-serif;
}

body {
  margin: 0;
  padding: 0;
  background-color: #f6f8ff;
}
</style>
