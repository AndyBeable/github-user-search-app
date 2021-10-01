<template>
  <div class="search-container">
    <img src="/public/assets/icon-search.svg" alt="" />
    <form class="search-input-form">
      <input
        type="text"
        class="input-field"
        name="input-field"
        placeholder="Search Github username"
      />
    </form>
    <div class="search-error">
      <p class="no-results">No results</p>
    </div>
    <button class="search-button">
      <p>Search</p>
    </button>
  </div>
</template>

<style scoped>
.search-container {
  display: flex;
}
</style>
