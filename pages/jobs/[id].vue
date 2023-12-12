<template>
  <input type="text" name="name" v-model="name">
  <p>あなたの名前は{{ name }}</p>
</template>

<script>
// nuxt3から導入されたref関数をvueのモジュールからimportしている
// [ref関数]_リアクティブ(状態管理)の値を定義するための関数
// https://field.asia/%E7%A5%9E%E5%9B%9Evue3-js-nuxt3-typescript%E3%81%A9%E3%81%86%E3%82%84%E3%82%8B%EF%BC%9F%E3%80%90%E3%82%BC%E3%83%AD%E3%81%8B%E3%82%89%E8%A7%A3%E8%AA%AC%E3%80%91/

import {ref} from 'vue'

export default {
  setup() {
    const name = ref("");

    return {
      name
    }
  }
}
</script>

<style>
</style>
