<script setup>
const props = defineProps({
    date: String,
    title: String,
    school: String
})
</script>

<template>
    <div class="edu-wrapper">
        <div class="desc-wrapper">
            <div class="edu-name">
                {{ title }}
            </div>
            <div class="edu-date">
                {{ date }}
            </div>
        </div>
        <div class="edu-skool">
            {{ school }}
        </div>
    </div>
</template>

<style scoped>
.edu-wrapper {
    display: flex;
    flex-direction: column;
    margin-left: 20px;
    margin-bottom: 20px;
}

.desc-wrapper {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1px;
}

.edu-name {
    font-size: 20px;
    font-weight: bold;
}

.edu-date {
    font-size: 20px;
    font-weight: bold;
}

.edu-skool {
    font-size: 18px;
    color: darkcyan;
}

@media all and (max-width: 1200px) {
    .edu-wrapper {
        width: 90%;
    }
}
</style>s