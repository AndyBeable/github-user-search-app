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
            <img :src="locationIcon" alt="Location" />
          </div>
          <h6 class="user-link-text">London, United Kingdom</h6>
        </div>
        <div class="user-website-container">
          <div class="user-website-icon">
            <img :src="websiteIcon" alt="" />
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
            <img :src="twitterIcon" alt="" />
          </div>
          <h6 class="user-link-text">Not available</h6>
        </div>
        <div class="user-company-container">
          <div class="user-company-icon">
            <img :src="companyIcon" alt="" />
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
import locationIcon from '../../../public/assets/icon-location.svg';
import websiteIcon from '../../../public/assets/icon-website.svg';
import twitterIcon from '../../../public/assets/icon-twitter.svg';
import companyIcon from '../../../public/assets/icon-company.svg';

export default {
  data() {
    return {
      locationIcon: locationIcon,
      websiteIcon: websiteIcon,
      twitterIcon: twitterIcon,
      companyIcon: companyIcon,
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

.user-location-container,
.user-website-container,
.user-twitter-container,
.user-company-container {
  display: flex;
  align-items: center;
}

.user-location-icon,
.user-website-icon,
.user-twitter-icon,
.user-company-container img {
  margin-right: 1rem;
}
</style>
