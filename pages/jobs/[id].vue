<template>
  <!-- テキスト入力とボタン -->
<input type="text" name="name" v-model="person.name">
<button type="button" @click="addSan">登録</button>

<!-- 名前を表示する部分 -->
<p>あなたの名前は<span class="u-tx-bold">{{ person.name }}</span></p>
</template>

<script language="ts">

import {ref,reactive} from 'vue'

// refとreactiveを使用して変数を定義している
export default {
setup() {
  // テキスト入力の値を保持する変数
  const name = ref('')
  // 'さん'がついた名前を保持する変数
  const nameWithSan = ref('')
  // オブジェクト形式でデータを保持する変数
  const person = reactive ({
    id: 1,
    name: 'sato',
    age: 20
  });
  // 'さん'を付けて名前を更新する関数
  const addSan = () => {
    nameWithSan.value = name.value + 'さん'
  };

  // コンポーネントに返すデータ
  return {
    name,
    nameWithSan,
    person,
    addSan
  }
}
}
</script>

<style>
.u-tx-bold {
font-weight: bold;
}
</style>