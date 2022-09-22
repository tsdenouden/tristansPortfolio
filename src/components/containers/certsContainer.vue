<script setup>
import { reactive } from '@vue/reactivity'
import certsCard from '../cards/certsCard.vue'

const certs_list = reactive([
  {
    "id": 1,
    "date": 2022,
    "title": "CS50x",
    "desc": "Harvard University"
  },
  {
    "id": 2,
    "date": 2019,
    "title": "Express Course",
    "subtitle": "Programming fundamentals course",
    "desc": "Sponsored by Microsoft"
  },
  {
    "id": 3,
    "date": 2022,
    "title": "Intermediate Machine Learning",
    "desc": "Kaggle"
  },
  {
    "id": 4,
    "date": 2022,
    "title": "Intro to Machine Learning",
    "desc": "Kaggle"
  },
  {
    "id": 5,
    "date": 2022,
    "title": "Pandas",
    "subtitle": "Python",
    "desc": "Kaggle"
  },
  {
    "id": 6,
    "date": 2021,
    "title": "Python is Easy",
    "subtitle": "Python 3 fundamentals",
    "desc": "Pirple"
  },
])
</script>

<template>
  <div class="education">
    <div v-for="cert in certs_list" :key="cert.id">
      <certsCard :date="cert.date" :title="cert.title" :subtitle="cert.subtitle" :desc="cert.desc"/>
    </div>
  </div>
</template>