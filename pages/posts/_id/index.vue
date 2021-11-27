<template>
  <v-container>
    <v-row>
      <v-col cols="10" class="mx-auto">
        <v-card>
          <v-card-title>
            <v-icon large left color="blue-grey"> mdi-cube </v-icon>
            <span class="text-h4">{{ post.title }}</span>
          </v-card-title>

          <v-img :src="post.appImage"></v-img>

          <v-card-text class="py-0">
            <p class="my-5">{{ post.content }}</p>
            <p>URL： {{ post.appUrl }}</p>
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
            <p class="mt-10">作成日： {{ post.createdAt }}</p>
            <p>最終更新日： {{ post.updatedAt }}</p>
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
                <span class="subheading mr-2">{{ post.likes.length }}</span>
                <v-icon class="mr-1"> mdi-comment-multiple-outline </v-icon>
                <span class="subheading mr-2">{{ post.comments.length }}</span>
              </v-row>
            </v-list-item>
          </v-card-actions>
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  props: {
    id: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      post: {
        id: 1,
        title: 'App Share',
        content:
          'みんなの作ったアプリを共有するアプリ。たくさん作ってたくさん共有しよう！',
        appImage: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
        appUrl: 'https://github.com/mizuki-n-2/app-share-web',
        tags: ['Go', 'Vue', 'MySQL', 'TypeScript', 'JavaScript'],
        createdAt: '2021/11/27 16:00',
        updatedAt: '2021/11/27 18:30',
        likes: [
          {
            userId: 1,
            userName: '浦島太郎',
          },
          {
            userId: 2,
            userName: '山田花子',
          },
        ],
        comments: [
          {
            userId: 1,
            userName: '浦島太郎',
            content: 'これは最高です！',
          },
          {
            userId: 2,
            userName: '山田花子',
            content: 'これは最高です！',
          },
        ],
        user: {
          id: 1,
          name: '浦島太郎',
          icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
        },
      },
    }
  },
})
</script>