<template>
  <section id="posts">
  <PostPreview
    v-for="post in posts"
    :key="post.id"
    :title="post.title"
    :excerpt="post.previewText"
    :thumbnailImage="post.thumbnailUrl"
    :id="post.id"/>




  </section>
</template>

<script>
import PostPreview from "@/components/Blog/PostPreview";

export default {
  components: {
    PostPreview
  },
 asyncData(context) {
   return context.app.$storyapi.get("cdn/stories", {
    version: "draft",
    starts_with: 'blog/'
  })
  .then(res => {
    console.log(res);
    return res;
  });
 }

  // data() {
    // return {
      // posts: [
      // {
          // title: "Thoughts On The State of MMA",
          // previewText: "Current state of MMA",
          // thumbnailUrl: "https://cdn.images.express.co.uk/img/dynamic/167/590x/Conor-McGregor-Khabib-Nurmagomedov-908222.jpg",
          // id: "state-of-MMA"
        // },
        // {
            // title: "Goat talk",
            // previewText: "talking about the current goat of MMA",
            // thumbnailUrl: "https://cdn.images.express.co.uk/img/dynamic/167/590x/Conor-McGregor-Khabib-Nurmagomedov-908222.jpg",
            // id: "goat-of-MMA"
          // }
      // ]
    // };
  // }
};
</script>

<style scoped>
  #posts{
    padding-top: 2rem;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
  }

  @media(min-width: 35rem) {
    #posts {
      flex-direction: row;

    }
  }
</style>
