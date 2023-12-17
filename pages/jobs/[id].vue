<template>
  <input type="text" name="name" v-model="person.name">
  <button type="button" @click="addSan">登録</button>

  <p>あなたの名前は<span class="u-tx-bold">{{ person.name }}</span></p>
  
  <!-- 条件付きでプロフィールを表示する部分 -->
  <button type="button" @click="showProfile">プロフィールを表示</button>
  <!-- isShowProfileがtrueなら情報が表示される -->
  <p v-if="isShowProfile">id: {{ person.id }}</p>
  <p v-if="isShowProfile">name: {{ person.name }}</p>
  <p v-if="isShowProfile">age: {{ person.age }}</p>
</template>

<script language="ts">

import { ref , reactive } from 'vue'

export default {
  setup() {
    const name = ref('')
    const nameWithSan = ref('')

    // refを使ってisShowProfileという変数を作成
    const isShowProfile = ref(false)

    const person = reactive ({
      id: 1,
      name: 'sato',
      age: 20
    });

    const addSan = () => {
      nameWithSan.value = name.value + 'さん'
    };

    // プロフィールを表示するボタンがクリックされると呼び出される
    // ボタンがクリックされるたびに表示非表示が切り替わる
    const showProfile = () => {
      isShowProfile.value = !isShowProfile.value
    }

    return {
      name,
      nameWithSan,
      person,
      isShowProfile,
      addSan,
      showProfile,
    }
  }
}
</script>

<style>
.u-tx-bold {
  font-weight: bold;
}
</style>
