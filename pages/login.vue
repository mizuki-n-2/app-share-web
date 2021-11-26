<template>
  <v-row justify="center">
    <v-col
      cols="12"
      sm="10"
      md="8"
      lg="6"
    >
      <v-card ref="form" class="mt-3">
        <v-card-title>ログイン</v-card-title>
        <v-card-text>
          <v-text-field
            v-model="email"
            :rules="[rules.required, rules.emailValid]"
            label="メールアドレス"
            required
          ></v-text-field>
          <v-text-field
            v-model="password"
            :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.passMin, rules.passMax]"
            :type="showPassword ? 'text' : 'password'"
            label="パスワード"
            hint="8文字以上30文字以下にしてください"
            counter
            required
            @click:append="showPassword = !showPassword"
          ></v-text-field>
        </v-card-text>
        <v-divider class="mt-3"></v-divider>
        <v-card-actions>
          <v-btn text>
            キャンセル
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn
            color="primary"
            text
            @click="submit"
          >
            ログイン
          </v-btn>
        </v-card-actions>
      </v-card>
    </v-col>
  </v-row>
</template>

<script lang="ts">
import Vue from 'vue'
export default Vue.extend({
  data () {
    return {
      email: '',
      password: '',
      showPassword: false,
      rules: {
        required: (value: string) => !!value || '必須入力項目です',
        emailValid: (value: string) => /^[a-zA-Z0-9.!#$%&’*+/=?^_`{|}~-]+@[a-zA-Z0-9-]+(?:\.[a-zA-Z0-9-]+)*$/.test(value) || 'メールアドレスの形式が正しくありません',
        passMin: (value: string) => (value && value.length >= 8) || 'パスワードは8文字以上にしてください',
        passMax: (value: string) => (value && value.length <= 30) || 'パスワードは30文字以下にしてください' 
      }
    }
  },
  methods: {
    submit () {
      // TODO
    }
  }
})
</script>