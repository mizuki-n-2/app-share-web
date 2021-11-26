<template>
  <v-card max-width="340">
    <v-img :src="post.appImage" height="180px"></v-img>

    <v-card-title>
      <v-icon large left color="success"> mdi-check-all </v-icon>
      <span class="text-h6">{{ post.title }}</span>
    </v-card-title>

    <v-card-text>
      <v-chip-group>
        <v-chip v-for="(tag, index) in post.tags" :key="index" color="info">
          {{ tag }}
        </v-chip>
      </v-chip-group>
    </v-card-text>

    <v-card-actions>
      <v-list-item class="grow">
        <v-list-item-avatar color="grey darken-3">
          <v-img class="elevation-6" alt="" :src="post.user.icon"></v-img>
        </v-list-item-avatar>

        <v-list-item-content>
          <v-list-item-title>{{ post.user.name }}</v-list-item-title>
        </v-list-item-content>

        <v-row align="center" justify="end">
          <v-icon class="mr-1"> mdi-thumb-up-outline </v-icon>
          <span class="subheading mr-2">{{ post.likeCount }}</span>
          <v-icon class="mr-1"> mdi-comment-multiple-outline </v-icon>
          <span class="subheading">{{ post.commentCount }}</span>
        </v-row>
      </v-list-item>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Post',
  data() {
    return {
      post: {
        id: 1,
        title: 'App Share',
        appImage: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
        tags: ['Go', 'Vue', 'MySQL'],
        updated_at: '2019-01-01',
        user: {
          id: 1,
          name: '浦島太郎',
          icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
        },
        likeCount: 256,
        commentCount: 45,
      },
    }
  },
})
</script>