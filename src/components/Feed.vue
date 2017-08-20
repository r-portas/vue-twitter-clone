<template>
  <div class="feed">
    <tweet v-for="tweet in tweets" :key="tweet.text + tweet.author" :content="tweet"></tweet>
  </div>
</template>

<style scoped>
.feed {
  padding: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-evenly;
}
</style>

<script>
import Tweet from './Tweet';

export default {
  name: 'feed',
  components: {
    Tweet,
  },
  props: [
    'tweets',
  ],
};
</script>
