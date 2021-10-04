<template>
  <div class="search-container">
    <div class="search-sub-container">
      <img :src="searchIcon" alt="" />
      <input
        v-model="query"
        class="search-input-form"
        type="text"
        name="input-field"
        placeholder="Search GitHub username..."
      />
    </div>
    <div class="button-container">
      <p v-if="hasError" class="no-results">No results</p>
      <button class="search-button" @click.prevent="search">
        Search
      </button>
    </div>
  </div>
</template>

<script>
import searchIcon from '../../../public/assets/icon-search.svg';

export default {
  props: {
    hasError: {
      type: Boolean,
      required: true,
    },
  },
  data() {
    return {
      searchIcon: searchIcon,
      query: '',
    };
  },
  methods: {
    search() {
      this.$emit('onSearch', this.query);
    },
  },
};
</script>

<style scoped>
.search-container {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  background-color: #fefefe;
  box-shadow: 0 16px 30px -10px rgb(70 96 187 / 20%);
  margin: 25px 0;
  border-radius: 15px;
  width: 100%;
  padding: 0.5rem 0;
}

@media screen and (min-width: 768px) {
  .search-container {
    width: 80%;
    justify-content: space-between;
    padding: 0.5rem 2.5rem;
  }
}

.search-sub-container {
  display: flex;
  align-items: center;
}
.search-sub-container img {
  margin: 0.5rem;
}

@media screen and (min-width: 768px) {
  .search-sub-container img {
    margin: 1rem;
  }
}

input {
  border: none;
  caret-color: #0079ff;
  line-height: 30px;
  width: 210px;
}

@media screen and (min-width: 768px) {
  input {
    width: 300px;
  }
}

button {
  background-color: #0079ff;
  color: #fefefe;
  border: none;
  border-radius: 10px;
  padding: 0.8rem 1.2rem;
  transition: 0.2s ease;
  cursor: pointer;
}

@media screen and (min-width: 768px) {
  button {
    padding: 1.2rem 2rem;
  }
}

button:hover {
  background-color: #60abff;
}

.button-container {
  display: flex;
}

p {
  color: #f74646;
  font-weight: 700;
  margin-right: 15px;
}
</style>
