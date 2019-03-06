<template>
    <Layout>
    <h1>{{ $page.redditPost.title }}</h1>
    <div>
      <g-image :src="$page.redditPost.img" :alt="$page.redditPost.title" class="imageReddit"/>
    </div>
    </div>
   </Layout>
</template>

<page-query>
    query RedditPost ($path: String!) {
          redditPost: redditPost(path: $path) {
              id
              title
              path
              img
          }
          
      }
</page-query>

<script>
export default {
  metaInfo () {
    return {
      title: this.$page.redditPost.title
    }
  }
}
</script>

<style scoped>
.imageReddit {
    max-width: 90%;
    max-height: 90%;
    margin-left: auto;
    margin-right: auto;
    display: block;
    width: auto;
    height: auto;
}
</style>
