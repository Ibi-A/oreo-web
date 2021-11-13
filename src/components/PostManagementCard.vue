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
        

            <picture-management-list :pictures="pictures"/>
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
import PictureManagementList from './PictureManagementList.vue'

export default {
  props: {
    id: String,
    title: String,
    date: String,
    description: String,
    pictures: [],
  },
  components: {
      PictureManagementList
  },
  data: () => ({
    show: false,
  }),
};
</script>
