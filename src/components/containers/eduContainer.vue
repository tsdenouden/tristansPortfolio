<script setup>
import { reactive } from '@vue/reactivity'
import eduCard from '../cards/eduCard.vue'

const edu_list = reactive([
  {
    "id": 1,
    "date": "2021-2023",
    "title": "CIE A Levels",
    "school": "LearnNow Distance Learning College"
  },
  {
    "id": 2,
    "date": "2019-2021",
    "title": "CIE IGCSE",
    "school": "Britus International School of Bahrain"
  }
])
</script>

<template>
    <div class="education">
        <div v-for="edu in edu_list" :key="edu.id">
        <eduCard :date="edu.date" :title="edu.title" :school="edu.school" />
        </div>
    </div>
</template>