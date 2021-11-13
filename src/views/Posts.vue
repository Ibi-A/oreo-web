<template>
  <v-container>
    <post-management-card
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
import Posts from "../data/posts.json";
import PostManagementCard from "../components/PostManagementCard.vue";

export default {
  components: {
    PostManagementCard,
  },
  data: () => ({
    posts: Posts,
  }),
};
</script>
