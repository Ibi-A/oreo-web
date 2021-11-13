<template>
  <v-card class="mx-auto" max-width="640">
    <v-carousel>
      <v-carousel-item
        v-for="picture in pictures"
        :key="picture"
        :src="picture.src"
      />
    </v-carousel>

    <v-card-title>
      {{ title }}
      <v-spacer></v-spacer>
      <v-btn icon @click="show = !show">
        <v-icon>{{ show ? "mdi-chevron-up" : "mdi-chevron-down" }}</v-icon>
      </v-btn>
    </v-card-title>

    <v-card-subtitle>{{ date }}</v-card-subtitle>

    <v-expand-transition>
      <div v-show="show">
        <v-divider></v-divider>
        <v-card-text>{{ description }}</v-card-text>
      </div>
    </v-expand-transition>
  </v-card>
</template>

<script>
export default {
  props: {
      id: String,
      title: String,
      date: String,
      description: String,
      pictures: []
  },
  data: () => ({
    show: false,
  }),
};
</script>
