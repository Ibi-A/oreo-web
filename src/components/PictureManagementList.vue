<template>
  <v-list subheader>
    <v-subheader inset>Pictures</v-subheader>
    <v-list-item v-for="picture in pictures" :key="picture">
      <v-list-item-avatar>
        <v-icon class="grey lighten-1" dark>mdi-file-image</v-icon>
      </v-list-item-avatar>
      <v-img :src="picture" max-width="250" />
      <v-spacer></v-spacer>
      <v-btn color="error" icon><v-icon>mdi-delete</v-icon></v-btn>
    </v-list-item>
  </v-list>
</template>

<script>
export default {
    props: {
        pictures: []
    }
}
</script>