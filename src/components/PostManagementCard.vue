<template>
  <v-card class="mx-auto mb-3" max-width="640">
    <v-card-title>
      <v-text-field v-model="title" />
      <v-spacer></v-spacer>
      <v-btn icon @click="show = !show">
        <v-icon>{{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon>
      </v-btn>
    </v-card-title>

    <v-card-subtitle>{{ date }}</v-card-subtitle>

    <v-card-text>
      <v-textarea v-model="description" />
    </v-card-text>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text>
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

        <v-file-input />
        </v-card-text>
      </div>
    </v-expand-transition>

    <v-card-actions>
      <v-btn color="primary">Update post</v-btn>
      <v-spacer></v-spacer>
      <v-btn color="error" plain>Delete post</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script>
export default {
  props: {
    id: String,
    title: String,
    date: String,
    description: String,
    pictures: [],
  },
  data: () => ({
    show: false,
  }),
};
</script>
