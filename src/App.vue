<template>
  <wrapper>
    <the-header></the-header>
    <search-bar @on-search="searchUser" :has-error="hasError"></search-bar>
    <user-card v-if="userData" :user="userData"></user-card>
  </wrapper>
</template>

<script>
import TheHeader from './components/layout/TheHeader.vue';
import Wrapper from './components/layout/Wrapper.vue';
import SearchBar from './components/ui/SearchBar.vue';
import UserCard from './components/ui/UserCard.vue';
import axios from 'axios';

export default {
  name: 'App',
  components: {
    TheHeader,
    Wrapper,
    SearchBar,
    UserCard,
  },
  data() {
    return {
      userData: null,
      hasError: false,
    };
  },
  created() {
    this.searchUser('octocat');
  },
  methods: {
    searchUser(query) {
      this.hasError = false;

      axios
        .get(`https://api.github.com/users/${query}`)
        .then((response) => {
          this.userData = response.data;
        })
        .catch(() => {
          this.hasError = true;
        });
    },
  },
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Space+Mono:wght@400;700&display=swap');

:root {
  --bg-light-color: #f6f8ff;
  --text-light-color: #4b6a9b;
}

* {
  box-sizing: border-box;
}

html {
  font-family: 'Space Mono', monospace, sans-serif;
}

body {
  margin: 0;
  padding: 0;
  background-color: var(--bg-light-color);
}

p {
  color: var(--text-light-color);
}

a,
a:visited {
  text-decoration: none;
  color: inherit;
}

h3,
h5 {
  margin-top: 0;
  margin-bottom: 0;
}

button,
input {
  font-family: 'Space Mono', monospace;
}

.opacity-50 {
  opacity: 50%;
}
</style>
