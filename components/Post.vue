<template>
  <v-card max-width="360" @click="goToDetail">
    <v-img :src="post.appImage" height="160px"></v-img>

    <v-card-title>
      <v-icon large left color="blue-grey"> mdi-cube </v-icon>
      <span class="text-h6">{{ post.title }}</span>
    </v-card-title>

    <v-card-text class="py-0">
      <v-chip-group column>
        <v-chip
          v-for="(tag, index) in post.tags"
          :key="index"
          color="info"
          outlined
        >
          {{ tag }}
        </v-chip>
      </v-chip-group>
    </v-card-text>

    <v-card-actions class="px-0 py-0">
      <v-list-item>
        <v-list-item-avatar color="grey darken-3">
          <v-img class="elevation-6" alt="" :src="post.user.icon"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>{{ post.user.name }}</v-list-item-title>
        </v-list-item-content>

        <v-row align="center" justify="end">
          <v-icon class="mr-1"> mdi-thumb-up-outline </v-icon>
          <span class="subheading mr-2">{{ post.likesCount }}</span>
          <v-icon class="mr-1"> mdi-comment-multiple-outline </v-icon>
          <span class="subheading mr-2">{{ post.commentsCount }}</span>
        </v-row>
      </v-list-item>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Post',
  props: {
    post: {
      type: Object,
      required: true,
    },
  },
  methods: {
    goToDetail() {
      this.$router.push({ path: `/posts/${this.post.id}` })
    },
  },
})
</script>