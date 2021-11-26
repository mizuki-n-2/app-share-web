<template>
  <v-row justify="center">
    <v-col
      cols="12"
      sm="10"
      md="8"
      lg="6"
    >
      <v-card ref="form" class="mt-3">
        <v-card-title>新規登録</v-card-title>
        <v-card-text>
          <v-text-field
            v-model="name"
            :rules="[rules.required, rules.nameMin, rules.nameMax]"
            label="名前"
            hint="2文字以上10文字以下にしてください"
            counter="10"
            required
          ></v-text-field>
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
          <v-text-field
            v-model="confirmPassword"
            :append-icon="showConfirmPassword ? 'mdi-eye' : 'mdi-eye-off'"
            :rules="[rules.required, rules.passMin, rules.passMax]"
            :type="showConfirmPassword ? 'text' : 'password'"
            label="パスワード(確認用)"
            counter
            required
            @click:append="showConfirmPassword = !showConfirmPassword"
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
            登録
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
      name: '',
      email: '',
      password: '',
      showPassword: false,
      showConfirmPassword: false,
      rules: {
        required: (value: string) => !!value || '必須入力項目です',
        nameMin: (value: string) => value.length >= 2 || '2文字以上入力してください',
        nameMax: (value: string) => value.length <= 10 || '10文字以下にしてください',
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