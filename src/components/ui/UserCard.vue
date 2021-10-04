<template>
  <div class="user-card-container">
    <div class="user-details-container">
      <div class="user-avatar">
        <img :src="avatar" alt="Avatar" />
      </div>
      <div class="user-details">
        <div>
          <h3>{{ name }}</h3>
          <h5>@{{ login }}</h5>
        </div>
        <div>
          <p>Joined {{ joined }}</p>
        </div>
      </div>
    </div>
    <div class="user-details-profile">
      <p>
        <!-- {{ bio }} -->
        Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ut omnis modi
        corporis.
      </p>
    </div>
    <div class="user-stats">
      <div class="stat">
        <h4>Repos</h4>
        <h2>{{ repos }}</h2>
      </div>
      <div class="stat">
        <h4>Followers</h4>
        <h2>{{ followers }}</h2>
      </div>
      <div class="stat">
        <h4>Following</h4>
        <h2>{{ following }}</h2>
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
          <h6 class="user-link-text">{{ twitter }}</h6>
        </div>
        <div class="user-company-container">
          <div class="user-company-icon">
            <img :src="companyIcon" alt="" />
          </div>
          <h6 class="user-link-text">
            {{ company }}
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
  props: [
    'avatar',
    'name',
    'login',
    'joined',
    'bio',
    'repos',
    'followers',
    'following',
    'location',
    'blog',
    'twitter',
    'company',
  ],
  data() {
    return {
      locationIcon: locationIcon,
      websiteIcon: websiteIcon,
      twitterIcon: twitterIcon,
      companyIcon: companyIcon,
    };
  },
  methods: {
    convertData() {
      console.log(this.joined);
    },
  },
};
</script>

<style scoped>
h5 {
  color: #0079ff;
  font-weight: 400;
}

.user-card-container {
  background-color: #fff;
  /* width: 80%; */
  padding: 1rem;
  border-radius: 15px;
  box-shadow: 0 3px 10px 3px #c4c9e470;
}

@media screen and (min-width: 768px) {
  .user-card-container {
    width: 80%;
  }
}

.user-details-container {
  display: flex;
  align-items: center;
}

.user-details-profile {
  width: 80%;
  margin: 0 auto;
}

.user-avatar img {
  width: 117px;
  border-radius: 100%;
  margin-right: 1rem;
}

.user-stats {
  display: flex;
  justify-content: space-evenly;
  text-align: center;
  background-color: #f6f8ff;
  margin: 0 auto;
  border-radius: 16px;
}

@media screen and (min-width: 768px) {
  .user-stats {
    width: 80%;
  }
}

.user-stats h4 {
  color: #4b6a9b;
  font-size: 12px;
  font-weight: 400;
}

.left-container {
  margin-right: 1rem;
}

.user-links {
  width: 80%;
  margin: 0 auto;
}

@media screen and (min-width: 768px) {
  .user-links {
    display: flex;
    justify-content: space-around;
  }
}

.user-location-container,
.user-website-container,
.user-twitter-container,
.user-company-container {
  display: flex;
  align-items: center;
  margin-bottom: -1.2rem;
}

@media screen and (min-width: 768px) {
  .user-location-container,
  .user-website-container,
  .user-twitter-container {
    display: flex;
    align-items: center;
  }
}

.user-location-icon,
.user-website-icon,
.user-twitter-icon,
.user-company-container img {
  margin-right: 1rem;
}
</style>
