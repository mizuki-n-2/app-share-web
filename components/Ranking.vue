<template>
  <v-card>
    <v-card-title class="primary white--text font-weight-bold">
      <v-icon color="yellow accent-3"> mdi-crown-outline </v-icon>
      <span>ユーザーランキング</span>
      <v-icon color="yellow accent-3"> mdi-crown-outline </v-icon>
    </v-card-title>

    <v-tabs right>
      <v-tab>いいね数</v-tab>
      <v-tab>投稿数</v-tab>
    </v-tabs>

    <v-card-text>
      <v-simple-table>
        <template #default>
          <tbody>
            <tr v-for="(user, index) in users" :key="user.id">
              <td>{{ index + 1 }}</td>
              <td>
                <v-list-item-avatar color="grey darken-3">
                  <v-img class="elevation-6" alt="" :src="user.icon"></v-img>
                </v-list-item-avatar>
                <span>{{ user.name }}</span>
              </td>
              <td>
                <v-icon class="mr-1" color="green accent-4"> mdi-thumb-up-outline </v-icon>
                <span class="text-h6">{{ user.likesCount }}</span>
              </td>
            </tr>
          </tbody>
        </template>
      </v-simple-table>
    </v-card-text>
  </v-card>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  name: 'Ranking',
  props: {
    users: {
      type: Array,
      required: true,
    },
  },
})
</script>