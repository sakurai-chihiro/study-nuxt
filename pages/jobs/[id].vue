<template>
  <input type="text" name="name" v-model="person.name">
  <button type="button" @click="addSan">登録</button>

  <p>あなたの名前は<span class="u-tx-bold">{{ person.name }}</span></p>
  
  <button type="button" @click="showProfile">プロフィールを表示</button>

  <p v-if="isShowProfile">id: {{ person.id }}</p>
  <p v-if="isShowProfile">name: {{ person.name }}</p>
  <p v-if="isShowProfile">age: {{ person.age }}</p>

  <!-- v-forディレクティブを使って求人情報を繰り返し表示する -->
  <ul>
    <li v-for="job in jobs" :key="job.id">
      <p :class="{ active:job.id == 2, active2:job.id == 3 }">
        求人ID: {{ job.id }}
      </p>
      <p>求人タイトル: {{ job.name }}</p>
      <p>求人内容: {{ job.content }}</p>
    </li>
  </ul>
</template>

<script language="ts">

import { ref , reactive } from 'vue'

export default {
  setup() {
    const name = ref('')
    const nameWithSan = ref('')

    const isShowProfile = ref(false)

    // 空の配列を初期値とするリアクティブ変数 jobs を作成
    const jobs = ref([])
    // jobsのvalueプロパティに、求人情報のオブジェクトを要素とする配列を代入
    jobs.value = [
      { id: 1,
        title: '求人1',
        content: '求人1の仕事内容です。'
      },
      { id: 2,
        title: '求人2',
        content: '求人2の仕事内容です。'
      },
      { id: 3,
        title: '求人3',
        content: '求人3の仕事内容です。'
      },
      { id: 4,
        title: '求人4',
        content: '求人4の仕事内容です。'
      },
    ];

    const person = reactive ({
      id: 1,
      name: 'sato',
      age: 20
    });

    const addSan = () => {
      nameWithSan.value = name.value + 'さん'
    };

    const showProfile = () => {
      isShowProfile.value = !isShowProfile.value
    }

    return {
      name,
      nameWithSan,
      person,
      isShowProfile,
      jobs,
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
