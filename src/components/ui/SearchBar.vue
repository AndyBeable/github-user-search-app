<template>
  <div class="search-container">
    <div class="search-sub-container">
      <img :src="searchIcon" alt="" />
      <input
        class="search-input-form"
        type="text"
        name="input-field"
        placeholder="Search GitHub username..."
      />
    </div>
    <div class="button-container">
      <!-- <p class="no-results">No results</p> -->
      <button class="search-button">
        Search
      </button>
    </div>
  </div>
</template>

<script>
import searchIcon from '../../../public/assets/icon-search.svg';

export default {
  data() {
    return {
      searchIcon: searchIcon,
    };
  },
};
</script>

<style scoped>
.search-container {
  display: flex;
  justify-content: space-between;
  background-color: #fefefe;
  box-shadow: 0 16px 30px -10px rgb(70 96 187 / 20%);
  padding: 5px 25px;
  margin: 25px 0;
  border-radius: 15px;
  width: 80%;
}

.search-sub-container {
  display: flex;
  align-items: center;
}
.search-sub-container img {
  margin: 1rem;
}

input {
  border: none;
  caret-color: #0079ff;
  line-height: 30px;
  width: 300px;
}

button {
  background-color: #0079ff;
  color: #fefefe;
  border-radius: 10px;
  padding: 1.2rem 2rem;
  border: none;
  transition: 0.2s ease;
  cursor: pointer;
}

button:hover {
  background-color: #60abff;
}
</style>
