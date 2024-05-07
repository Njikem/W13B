<template>
  <div id="body">
   
   <button v-on:click="toggle">toggle</button>
    <div ref="tweets-container" class="tweets-container">
      <div class="card" v-for="(tweet, i ) in tweets" :key="`tweet-${i}`">
        <div >
          <p>{{ tweet.tweetContent }}</p>
          <h3>{{ tweet.user }}</h3>
          <h3>{{ tweet.date_created }}</h3>
        </div>
      </div>
    </div>
  </div>
</template>

<script>

export default {
  name: 'MyBody',
  components: { 
   
  },
  methods:{
    toggle: function() {
      console.log("toggle")
      const container = this.$refs['tweets-container'];
      if (container.style.display === 'grid') {
        console.log("ITs grid")
        container.style.display = 'block'
      } else {
        container.style.display = 'grid';
      }
    }
  },
  data: function() {
    return {
    
      tweets: [
        {
          tweetContent: ' A tweet is a short, high-pitched sound made by a small bird.A tweet is a short message from someone on the Twitter website. She regretted posting.',
          user: 'Mary',
          date_created: '2021-15-10' 
        },
        {
          tweetContent: ' A tweet is a short, high-pitched sound made by a small bird.A tweet is a short message from someone on the Twitter         website. She regretted posting.',
          user: 'John',
          date_created: '2019-05-11' 
        }
      ],
    }
  },
 
  
  }
</script>

<style>
  .card {
    border: 1px solid black;
    margin-top: 15px;
    width: 300px;

  }

  .tweets-container {
    display: block;
    grid-template-columns: 1fr 1fr 1fr;
  }
</style>
