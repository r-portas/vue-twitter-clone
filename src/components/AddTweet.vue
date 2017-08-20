<template>
  <div class="card my-card">
    <h4 class="card-title">Post Tweet</h4>
    <div class="card-body">
      <div class="input-group">
        <span class="input-group-addon" id="addon1">@</span>
        <input v-model="username" type="text" class="form-control" placeholder="Username" aria-label="Username" aria-describedby="addon1">
      </div>
      <div class="input-group">
        <input v-model="tweet" type="text" class="form-control" placeholder="Tweet" aria-label="Tweet">
      </div>
      <div class="input-group">
        <button @click="addTweet" type="button" class="btn btn-primary">Tweet!</button>
      </div>
    </div>
  </div>
</template>

<style scoped>
.my-card {
  padding: 10px;
  margin: 10px;
}

.my-card .input-group {
  padding: 5px;
}

.my-card button {
  width: 100%;
}
</style>

<script>
export default {
  name: 'add-tweet',
  props: [
    'onAdd',
  ],
  data() {
    return {
      username: '',
      tweet: '',
    };
  },
  methods: {
    addTweet() {
      if (this.username !== '' && this.tweet !== '') {
        this.onAdd(this.username, this.tweet);
        this.tweet = '';
      }
    },
  },
};
</script>
