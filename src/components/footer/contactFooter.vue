<script setup>
const props = defineProps({
    heading: String,
    email: String
})
</script>

<template>
    <div class="contact_heading">
        {{ heading }}
    </div>
    <div class="links">
        <div class="contact_email">
            {{ email }}
        </div>
        <div class="icons">
            <a href="" target="_blank" rel="noopener noreferrer">
                <img src="../../assets/icons/github-original.svg" alt="">
            </a>
            <a href="" target="_blank" rel="noopener noreferrer">
                <img src="../../assets/icons/behance-plain.svg" alt="">
            </a>
            <a href="" target="_blank" rel="noopener noreferrer">
                <img src="../../assets/icons/yt-icon-dark.png" alt="">
            </a>
        </div>
    </div>
</template>

<style scoped>
.icons {
    margin-inline: 40px;
}
</style>