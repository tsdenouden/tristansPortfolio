<script setup>
const props = defineProps({
    date: Number,
    title: String,
    subtitle: String,
    desc: String
})
</script>

<template>
    <div class="certs-wrapper">
        <div class="certs-info">
            <div class="certs-name">
                {{ title }} 
                <div v-if="subtitle" class="certs-sub">
                    <span>({{ subtitle }})</span>
                </div>
            </div>
            <div class="certs-date">
                {{ date }}
            </div>
        </div>
        <div class="certs-desc">
            {{ desc }}
        </div>
    </div>
</template>

<style scoped>
.certs-wrapper {
    display: flex;
    flex-direction: column;
    margin-left: 20px;
    margin-bottom: 20px;
}

.certs-info {
    display: flex;
    justify-content: space-between;
    margin-bottom: 1px;
}

.certs-name {
    font-size: 20px;
    font-weight: bold;
}

.certs-sub {
    font-size: 18px;
}

.certs-date {
    font-size: 20px;
    font-weight: bold;
}

.certs-desc {
    font-size: 18px;
    color: darkcyan;
}

@media all and (max-width: 1200px) {
    .certs-wrapper {
        width: 90%;
    }
}
</style>