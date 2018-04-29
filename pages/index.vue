<template>
  <section class="container">
    <nuxt-link
    v-for="post in post"
    :key="post.id"
    :to="post.id">
    <article class="post-preview"></article>
    </nuxt-link>


  </section>
</template>

<script>


export default {
  data() {
    return {
      posts: [
      {
          title: "Thoughts On The State of MMA",
          previewText: "Current state of MMA",
          thumbnailURL: "https://cdn.images.express.co.uk/img/dynamic/167/590x/Conor-McGregor-Khabib-Nurmagomedov-908222.jpg",
          id: "state-of-MMA"
        },
        {
            title: "Goat talk",
            previewText: "talking about the current goat of MMA",
            thumbnailURL: "https://cdn.images.express.co.uk/img/dynamic/167/590x/Conor-McGregor-Khabib-Nurmagomedov-908222.jpg",
            id: "goat-of-MMA"
          }
      ]
    };
  }
};
</script>

<style>

</style>
