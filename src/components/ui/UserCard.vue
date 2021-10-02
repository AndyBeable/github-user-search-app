<template>
  <div class="user-card-container">
    <div class="user-details-container">
      <div class="user-avatar">
        <img src="" alt="" />
      </div>
      <div class="user-details">
        <h3>User Name</h3>
        <h5>@Username</h5>
        <p>Joined 1 October 2021</p>
      </div>
    </div>
    <div class="user-details-profile">
      <p>
        Lorem ipsum, dolor sit amet consectetur adipisicing elit. Eligendi aut
        facere, nihil, veritatis ut omnis cupiditate reiciendis.
      </p>
    </div>
    <div class="user-stats">
      <div class="stat">
        <p>Repos</p>
        <p>8</p>
      </div>
      <div class="stat">
        <p>Followers</p>
        <p>82343</p>
      </div>
      <div class="stat">
        <p>Following</p>
        <p>80</p>
      </div>
    </div>
    <div class="user-links">
      <div class="left-container">
        <div class="user-location-container">
          <div class="user-location-icon">
            <img :src="image" alt="Location" />
          </div>
          <h6 class="user-link-text">London, United Kingdom</h6>
        </div>
        <div class="user-github-container">
          <div class="user-github-icon">
            <img src="" alt="" />
          </div>
          <h6 class="user-link-text">
            <a href="https://github.com/AndyBeable">
              https://github.com/AndyBeable
            </a>
          </h6>
        </div>
      </div>
      <div class="right-container">
        <div class="user-twitter-container">
          <div class="user-twitter-icon">
            <img src="" alt="" />
          </div>
          <h6 class="user-link-text">Not available</h6>
        </div>
        <div class="user-company-container">
          <div class="user-company-icon">
            <img src="" alt="" />
          </div>
          <h6 class="user-link-text">
            Freelancer
          </h6>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import image from '../../../public/assets/icon-location.svg';

export default {
  data() {
    return {
      image: image,
    };
  },
};
</script>

<style scoped>
.user-card-container {
  background-color: #fff;
  width: 80%;
  padding: 1rem;
  border-radius: 15px;
  box-shadow: 0 3px 10px 3px #c4c9e470;
}

.user-stats {
  display: flex;
}

.user-links {
  display: flex;
}
</style>
