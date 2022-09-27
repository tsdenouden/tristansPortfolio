<script setup>
const props = defineProps({
    heading: String,
    email: String
})
</script>

<template>
    <div class="contact-wrapper">
        <div>
            <div class="contact-header">
                {{ heading }}
            </div>
            <div class="contact-email">
                {{ email }}
            </div>
        </div>

        <div class="contact-icons">
            <a href="https://github.com/tsdenouden" target="_blank" rel="noopener noreferrer">
                <img src="../../assets/icons/github-original.svg" alt="">
            </a>
            <a href="https://www.behance.net/tristandenouden" target="_blank" rel="noopener noreferrer">
                <img src="../../assets/icons/behance-plain.svg" alt="">
            </a>
            <a href="https://www.youtube.com/channel/UCFtJ-g7eYrA9LUcaSOiBBBA" class="yt-icon" target="_blank" rel="noopener noreferrer">
                <img src="../../assets/icons/yt-icon-dark.png" alt="">
            </a>
        </div>
    </div>
</template>

<style scoped>
.contact-wrapper {
    display: flex;
    flex-direction: column;
    margin-bottom: 50px;
}

.contact-header {
    font-size: 60px;
    font-weight: bold;
}

.contact-email {
    color: lightseagreen;
    font-size: 30px;
    font-weight: bold;
    margin-bottom: 20px;
}

.contact-icons {
    display: flex;
    margin-inline: 5px;
}

.contact-icons > a {
    width: 4%;
    height: auto;
    margin-inline: 10px;
}

.contact-icons > .yt-icon {
    width: 5.5%;
    height: auto;
}

.contact-icons > a > img {
    width: 100%;
    height: auto;
}

@media all and (max-width: 1200px) {
    .contact-icons > a {
        width: 10%;
    }

    .contact-icons > .yt-icon {
        width: 14%;
    }
}
</style>