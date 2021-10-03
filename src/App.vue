<template>
  <wrapper>
    <the-header></the-header>
    <search-bar></search-bar>
    <user-card
      :name="userData.name"
      :login="userData.login"
      :joined="userData.created_at"
      :bio="userData.bio"
      :repos="userData.public_repos"
      :followers="userData.followers"
      :following="userData.following"
      :location="userData.location"
      :blog="userData.blog"
      :twitter="userData.twitter_username"
      :company="userData.company"
    ></user-card>
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
    };
  },
  created: function() {
    axios.get('https://api.github.com/users/AndyBeable').then((response) => {
      this.userData = response.data;
      console.log(this.userData);
    });
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
