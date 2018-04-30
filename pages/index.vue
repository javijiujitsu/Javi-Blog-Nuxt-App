<template>
  <section class="container">
    <nuxt-link
    v-for="post in posts"
    :key="post.id"
    :to="post.id">
    <article class="post-preview">
      <div
        :style="{backgroundImage: post.thumbnailUrl}"
        class="post-preview-thumbnail"></div>
      <div class="post-preview-content">
        <h1>{{ post.title}}</h1>
        <p>{{post.previewText}}</p>
      </div>
    </article>
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
          thumbnailUrl: "https://cdn.images.express.co.uk/img/dynamic/167/590x/Conor-McGregor-Khabib-Nurmagomedov-908222.jpg",
          id: "state-of-MMA"
        },
        {
            title: "Goat talk",
            previewText: "talking about the current goat of MMA",
            thumbnailUrl: "https://cdn.images.express.co.uk/img/dynamic/167/590x/Conor-McGregor-Khabib-Nurmagomedov-908222.jpg",
            id: "goat-of-MMA"
          }
      ]
    };
  }
};
</script>

<style>

</style>
