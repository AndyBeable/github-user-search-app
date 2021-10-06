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
  emits: ['onSearch'],
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
      this.query = '';
    },
  },
};
</script>

<style scoped>
.search-container {
  display: flex;
  align-items: center;
  justify-content: space-evenly;
  background-color: var(--bg-white);
  box-shadow: 0 16px 30px -10px rgb(70 96 187 / 20%);
  margin: 25px 0;
  border-radius: 15px;
  width: 100%;
  padding: 0.5rem 0;
}

.LIGHT .search-container {
  background-color: var(--bg-dark-color-2);
  box-shadow: none;
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
  caret-color: var(--light-blue);
  line-height: 30px;
  width: 185px;
  background-color: inherit;
}

@media screen and (min-width: 768px) {
  input {
    width: 300px;
  }
}

.LIGHT input[type='text']::placeholder {
  color: var(--bg-white);
}

button {
  background-color: var(--light-blue-bold);
  color: var(--bg-light-color);
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
  background-color: var(--light-blue);
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
