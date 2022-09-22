<script setup>
const props = defineProps({
    year: Number,
    grade: Number,
    title: String,
    subtitle: String,
    body: String,
    image: String,
    imageAlt: String,
    tools: Array[String],
    github: String
})


// retrieve image src in project-thumbnails based on name
const getImgUrl = (pic) => {
    const images = require.context('../../assets/project-thumbnails', false, /\.png$/)
    return images('./' + pic + '.png')
}
</script>

<template>
    <!-- Project ifno -->
    <div class="info">
        <div class="yearngrade">
            <div>
                {{ year }}
            </div>
            <div v-if="grade">
                Grade: {{ grade }}%
            </div>
        </div>
        <div class="projectname">
            {{ title }} <span class="sub_title">{{ subtitle }}</span>
        </div>
        <div class="projectbody">
            {{ body }}
        </div>
        <div class="tools">
            Tools used: {{ tools }}
            <a :href="github" target="_blank" rel="noopener noreferrer">Github</a>
        </div>
    </div>
    <!-- Project image preview -->
    <div v-if="image" class="img">
        <img :src="getImgUrl(image)" :alt="imageAlt">
    </div>
</template>