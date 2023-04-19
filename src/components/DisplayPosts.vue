<template>
  <div>
    <button @click='toggle'>{{togglepost}}</button>
    <article v-if='listlayout === true'>
      <div v-for='(posts, i) in posts' :key='i'>
        <p>{{ posts['content'] }}</p>
        <p>{{ posts['user'] }}</p>
        <h5>{{ posts['date_created'] }}</h5>
      </div>
    </article>
    <article v-else>
      <div v-for='(posts, i) in posts' :key='i'>
        <p>{{ posts['content'] }}</p>
        <p>{{ posts['user'] }}</p>
        <h5>{{ posts['date_created'] }}</h5>
      </div>
    </article>
  </div>
</template>

<script>
export default {
//
computed: {
    togglepost() {
        return this.listlayout ? "Grid View": "List View";
    }
},


    //creating function for the toggle button
  methods: {
    toggle: function () {
      this.listlayout = !this.listlayout
    }
  },
    // creating variable for the posts
  data: function () {
    return {
      listlayout: true,
      posts: [
        {
          content:
            "Whether you are a small business owner or you have some things from around the house you want to get rid of, you are likely looking to reach a wider number of people and increase the likelihood that you will find new customers or connect with the right buyer. One helpful way of reaching a wider variety of people is to post ads about your business or items online. As people are browsing and searching for keywords that match what’s in your ad, there is a greater chance they will land on your post and get in touch with you. And fortunately, many of the online classifieds sites where you can post your ad are free to use. Learn some important things to consider about the process of posting a free ad online",
          user: "Staff Writer",
          date_created: "9-14-2020",
        },
        {

          content:
            "Choose the Right Site: Craigslist, eBay, Facebook — these and other websites all give you options for posting your ad and reaching people. However, there are some key differences in them that you will want to consider before you start posting everywhere in a flurry. Save time by keeping your focus on the sites that are more likely to get you the results you are looking for",
          user: "kate",
          date_created: "5-8-2021",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
</style>