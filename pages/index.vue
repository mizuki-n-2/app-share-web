<template>
  <v-container>
    <v-row class="d-flex">
      <v-col class="left" cols="8">
        <p class="font-italic">あなたの作ったアプリを共有しよう！</p>
        <div class="d-flex justify-end">
          <v-toolbar flat max-width="400px">
            <v-text-field
              v-model="search"
              append-icon="mdi-magnify"
              label="検索"
              single-line
            ></v-text-field>
          </v-toolbar>
        </div>

        <v-tabs>
          <v-tab>新着順</v-tab>
          <v-tab>人気順</v-tab>
        </v-tabs>
        <v-row class="d-flex mt-2">
          <v-col v-for="post in posts" :key="post.id" cols="6">
            <Post :post="post" class="mx-auto" />
          </v-col>
        </v-row>
      </v-col>

      <v-col class="right" cols="4">
        <Ranking :users="users" />
      </v-col>
    </v-row>
  </v-container>
</template>

<script lang="ts">
import Vue from 'vue'
import Post from '../components/Post.vue'
import Ranking from '../components/Ranking.vue'
export default Vue.extend({
  components: {
    Post,
    Ranking,
  },
  data() {
    return {
      posts: [
        {
          id: 1,
          title: 'App Share',
          appImage: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
          tags: ['Go', 'Vue', 'MySQL', 'TypeScript', 'JavaScript'],
          user: {
            id: 1,
            name: '浦島太郎',
            icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
          },
          likesCount: 256,
          commentsCount: 45,
        },
        {
          id: 2,
          title: 'App Share',
          appImage: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
          tags: ['Go', 'Vue', 'MySQL'],
          user: {
            id: 1,
            name: '浦島太郎',
            icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
          },
          likesCount: 256,
          commentsCount: 45,
        },
        {
          id: 3,
          title: 'App Share',
          appImage: 'https://cdn.vuetifyjs.com/images/cards/sunshine.jpg',
          tags: ['Go', 'Vue', 'MySQL'],
          user: {
            id: 1,
            name: '浦島太郎',
            icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
          },
          likesCount: 256,
          commentsCount: 45,
        },
      ],
      users: [
        {
          id: 1,
          name: '浦島太郎',
          icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
          likesCount: 256,
          postsCount: 45,
        },
        {
          id: 2,
          name: '浦島太郎',
          icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
          likesCount: 240,
          postsCount: 23
        },
        {
          id: 3,
          name: '浦島太郎',
          icon: 'https://avataaars.io/?avatarStyle=Transparent&topType=ShortHairShortCurly&accessoriesType=Prescription02&hairColor=Black&facialHairType=Blank&clotheType=Hoodie&clotheColor=White&eyeType=Default&eyebrowType=DefaultNatural&mouthType=Default&skinColor=Light',
          likesCount: 50,
          postsCount: 4
        },
      ],
    }
  },
  mounted() {},
  methods: {},
})
</script>