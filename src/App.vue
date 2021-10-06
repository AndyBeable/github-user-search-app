<template>
  <div class="app" :class="isDark ? 'DARK' : 'LIGHT'">
    <wrapper>
      <the-header :is-dark="isDark" @toggle-mode="toggleMode"></the-header>
      <search-bar @on-search="searchUser" :has-error="hasError"></search-bar>
      <user-card v-if="userData" :user="userData"></user-card>
    </wrapper>
  </div>
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
      isDark: false,
    };
  },
  created() {
    this.searchUser('octocat');
  },
  methods: {
    toggleMode() {
      this.isDark = !this.isDark;
    },
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
  --white: #fff;
  --black: #000;
  --dark-blue: #1e2a47;
  --darker-blue: #141d2f;
  --blue: #0079ff;
  --light-blue: #60abff;
  --grey: #697c9a;
  --blue-grey: #4b6a9b;
  --light-grey: #f6f8ff;

  --bg-color: var(--light-grey);
  --card-bg: var(--white);
  --heading-color: var(--black);
  --text-color: var(--blue-grey);
}

.DARK {
  --bg-color: var(--dark-blue);
  --card-bg: var(--darker-blue);
  --heading-color: var(--white);
  --text-color: var(--white);
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
}

.app {
  background-color: var(--bg-color);
}

p {
  color: var(--text-color);
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
  color: #ffffff;
}
</style>
