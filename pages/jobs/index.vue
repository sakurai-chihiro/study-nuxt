<template>
  <h2>求人一覧</h2>
  <ul>
    <li v-for="job in jobs" :key="job.id">
      <p>求人ID: {{ job.id }}</p>
      <p>求人タイトル: {{ job.title }}</p>
      <p>求人内容: {{ job.description }}</p>
      <p>画像：<img :src="job.cover" alt=""></p>
    </li>
  </ul>
</template>

<script lang="ts">
import { ref,reactive } from 'vue'

export default {
  async setup() {
    const { data: jobs } = await useFetch(`https://62fe320941165d66bfbabe7e.mockapi.io/apt/v1/jobs`)
    return {
      jobs,
    }
  }
}
</script>