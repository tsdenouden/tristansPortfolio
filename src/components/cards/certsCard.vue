<script setup>
const props = defineProps({
    date: Number,
    title: String,
    subtitle: String,
    desc: String
})
</script>

<template>
    <div class="info">
        <div class="name">
            {{ title }} 
            <div v-if="subtitle" class="edu_sub">
                <span>{{ subtitle }}</span>
            </div>
        </div>
        <div class="date">
            {{ date }}
        </div>
    </div>
    <div class="desc">
        {{ desc }}
    </div>
</template>