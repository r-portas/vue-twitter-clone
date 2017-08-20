<template>
  <div class="card tweet">
    <h4 class="card-title">{{content.tweet}}</h4>
    <h6 class="card-subtitle mb-2 text-muted">- {{content.author}}</h6>
  </div>
</template>

<style scoped>
.tweet {
  padding: 10px;
}
</style>

<script>
export default {
  name: 'tweet',
  props: [
    'content',
  ],
};
</script>
