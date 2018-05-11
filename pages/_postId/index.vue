<template>
  <div id="post">
    <div class="post-thumbnail"></div>
    <h1></h1>
    <p></p>
  </div>



</template>

<script>
export default {
    asyncData(context){
      return context.app.$storyapi
      .get("cdn/stories/blog/" + context.params.postId, {
        version: "draft"
      })
      .then(res =>  {
          console.log(res.data);

      });
    }
};



</script>
