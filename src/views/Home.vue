<template>
  <v-container>
    <post-card
      v-for="post in posts"
      :key="post"
      :id="post.id"
      :title="post.title"
      :description="post.description"
      :date="post.date"
      :pictures="post.pictures"
      />
  </v-container>
</template>

<script>
import Posts from '../data/posts.json'
import PostCard from "../components/PostCard.vue";

export default {
  components: {
    PostCard,
  },
  data: () => ({
    posts: Posts
  })
};
</script>
