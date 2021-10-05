<template>
  <div class="app" :class="mode">
    <wrapper>
      <the-header :mode="mode" @toggle-mode="toggleMode"></the-header>
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
      mode: 'DARK',
    };
  },
  created() {
    this.searchUser('octocat');
  },
  methods: {
    toggleMode() {
      console.log('clicked');
      if (this.mode === 'DARK') {
        this.mode = 'LIGHT';
      } else {
        this.mode = 'DARK';
      }
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
  --bg-light-color: #f6f8ff;
  --bg-white: #fefefe;
  --text-light-color: #4b6a9b;
  --bg-dark-color: #141d2f;
  --bg-dark-color-2: #1e2a47;
  --text-dark-color: #ffffff;
  --light-blue-bold: #0079ff;
  --light-blue: #60abff;
  --light-grey: #697c9a;
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
  background-color: var(--bg-light-color);
}

.LIGHT {
  background: var(--bg-dark-color);
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
  opacity: 90%;
}
</style>
