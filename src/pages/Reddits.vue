<template>
  <Layout>
    
    <h1>Awww Reddits!</h1>
   
    <ul>
      <li v-for="post in $page.posts.edges" :key="$page.posts.edges.id">
        <g-link :to="post.node.path">{{ post.node.title }}</g-link>
      </li>
    </ul>
    <p class="home-links">
      <a href="https://gridsome.org/docs" target="_blank" rel="noopener">Gridsome Docs</a>
      <a href="https://github.com/gridsome/gridsome" target="_blank" rel="noopener">GitHub</a>
    </p>

  </Layout>
</template>

<page-query>
query RedditPosts{
posts: allRedditPost {
  edges {
    node {
      id
      title
      thumbnail
      path
      img
      content
      slug
    }
  }
}
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
.home-links a {
  margin-right: 1rem;
}
</style>
