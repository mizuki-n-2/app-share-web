<template>
  <div>
    <Post />
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import Post from '../components/Post.vue'
export default Vue.extend({
  components: {
    Post
  },
  data() {
    return {
      posts: []
    }
  },
  mounted() {
    
  },
  methods: {
    
  }
})
</script>