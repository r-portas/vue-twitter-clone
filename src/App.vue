<template>
  <div id='app'>
    <nav class='navbar navbar-light bg-light'>
      <a class='navbar-brand' href='#'>Twitter Clone</a>
    </nav>
    <!-- <img src='./assets/logo.png'> -->
    <feed :tweets='tweets'></feed>
    <add-tweet :onAdd='addTweet'></add-tweet>
  </div>
</template>

<script>
  import Firebase from 'firebase';
  import Feed from './components/Feed';
  import AddTweet from './components/AddTweet';

  const config = {
    apiKey: 'AIzaSyDr8S9kPPvECw2hAdnWOicMkXnUKeehN_s',
    authDomain: 'twitter-clone-5d74a.firebaseapp.com',
    databaseURL: 'https://twitter-clone-5d74a.firebaseio.com',
    projectId: 'twitter-clone-5d74a',
    storageBucket: 'twitter-clone-5d74a.appspot.com',
    messagingSenderId: '117450095676',
  };
  const firebaseApp = Firebase.initializeApp(config);
  const db = firebaseApp.database();

  export default {
    name: 'app',

    firebase: {
      tweets: db.ref('tweets'),
    },

    components: {
      Feed,
      AddTweet,
    },

    data() {
      return {
        firebaseApp: null,
      };
    },

    methods: {
      addTweet(author, tweet) {
        this.$firebaseRefs.tweets.push({
          author,
          tweet,
        });
      },
    },
  };
</script>

<style>
#app {
}
</style>
