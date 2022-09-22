<script setup>
const props = defineProps({
    date: String,
    title: String,
    school: String
})
</script>

<template>
    <div class="info">
        <div class="name">
            {{ title }}
        </div>
        <div class="date">
            {{ date }}
        </div>
    </div>
    <div class="skool">
        {{ school }}
    </div>
</template>