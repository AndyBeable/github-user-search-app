<template>
  <div class="user-card-container">
    <div class="user-details-container">
      <div class="user-avatar">
        <img :src="user.avatar_url" :alt="user.name" />
      </div>
      <div class="user-details">
        <div>
          <h3>{{ user.name }}</h3>
          <h5>@{{ user.login }}</h5>
        </div>
        <div>
          <p>Joined {{ moment(user.created_at).format('MMM DD YYYY') }}</p>
        </div>
      </div>
    </div>
    <div class="user-details-profile">
      <p v-if="user.bio">
        {{ user.bio }}
      </p>
      <p v-else>This profile has no bio.</p>
    </div>
    <div class="user-stats">
      <div class="stat">
        <h4>Repos</h4>
        <h2>{{ user.public_repos }}</h2>
      </div>
      <div class="stat">
        <h4>Followers</h4>
        <h2>{{ user.followers }}</h2>
      </div>
      <div class="stat">
        <h4>Following</h4>
        <h2>{{ user.following }}</h2>
      </div>
    </div>
    <div class="user-links">
      <div class="left-container">
        <div class="user-location-container">
          <div class="user-location-icon">
            <img :src="locationIcon" alt="Location" />
          </div>
          <p class="user-link-text">London, United Kingdom</p>
        </div>
        <div
          class="user-website-container"
          :class="{ 'opacity-50': !user.blog }"
        >
          <div class="user-website-icon">
            <img :src="websiteIcon" alt="" />
          </div>
          <p class="user-link-text">
            <a v-if="user.blog" :href="user.blog" target="_blank">
              {{ user.blog }}
            </a>
            <span v-else>Not available</span>
          </p>
        </div>
      </div>
      <div class="right-container">
        <div
          class="user-twitter-container"
          :class="{ 'opacity-50': !user.twitter_username }"
        >
          <div class="user-twitter-icon">
            <twitter-icon />
          </div>
          <p class="user-link-text">
            <a v-if="user.twitter_username" :href="twitterUrl" target="_blank">
              {{ user.twitter_username }}
            </a>
            <span v-else>Not available</span>
          </p>
        </div>
        <div
          class="user-company-container"
          :class="{ 'opacity-50': !user.company }"
        >
          <div class="user-company-icon">
            <company-icon />
          </div>
          <p v-if="user.company" class="user-link-text">
            {{ user.company }}
          </p>
          <p v-else>Not available</p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import locationIcon from '../../../public/assets/icon-location.svg';
import websiteIcon from '../../../public/assets/icon-website.svg';

import CompanyIcon from '../../components/icons/Company.vue';
import TwitterIcon from '../../components/icons/Twitter.vue';

import moment from 'moment';

export default {
  props: ['user'],
  components: { TwitterIcon, CompanyIcon },
  data() {
    return {
      moment: moment,
      locationIcon: locationIcon,
      websiteIcon: websiteIcon,
    };
  },
  computed: {
    twitterUrl() {
      return `http://twitter.com/${this.user.twitter_username}`;
    },
    companyUrl() {
      return this.user.organizations_url;
    },
  },
};
</script>

<style scoped>
h5 {
  color: var(--blue);
  font-weight: 400;
}

.user-card-container {
  background-color: var(--card-bg);
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

@media screen and (min-width: 768px) {
  .user-details {
    display: flex;
    justify-content: space-between;
    width: 72%;
  }
}

.user-details h3 {
  color: var(--heading-color);
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
  background-color: var(--bg-color);
  margin: 0 auto;
  border-radius: 16px;
}

.user-stats h2 {
  color: var(--heading-color);
}

.user-stats h4 {
  color: var(--text-color);
}

@media screen and (min-width: 768px) {
  .user-stats {
    width: 80%;
  }
}

.user-stats h4 {
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

.user-link-text {
  color: var(--text-color);
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
.user-company-icon {
  margin-right: 1rem;
}

.DARK .user-card-container {
  box-shadow: none;
}
</style>
