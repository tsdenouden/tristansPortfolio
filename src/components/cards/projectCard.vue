<script setup>
const { onMounted, ref }=require("@vue/runtime-core")

const props = defineProps({
    year: Number,
    grade: Number,
    title: String,
    subtitle: String,
    body: String,
    image: String,
    imageAlt: String,
    tools: Array[String],
    mobileTools: Array[String],
    github: String,
    itchio: String
})


// retrieve image src in project-thumbnails based on name
const getImgUrl = (pic) => {
    const images = require.context('../../assets/project-thumbnails', false, /\.png$/)
    return images('./' + pic + '.png')
}


// update viewport width & check for breakpoint
const viewWidth = ref(window.innerWidth)
const mdBreakpoint = ref(false)

onMounted(() => {
    updateWidth()
    window.addEventListener('resize', updateWidth)
})

const updateWidth = () => {
    viewWidth.value = window.innerWidth
    if (viewWidth.value <= 1200) {
        mdBreakpoint.value = true;
    } else {
        mdBreakpoint.value = false;
    }
}
</script>

<template>
    <!-- Project info -->
    <div class="project-card">
        <div class="info">
            <div class="yearngrade">
                <div>
                    {{ year }}
                </div>
                <div v-if="grade">
                    Grade: {{ grade }}%
                </div>
            </div>
            <div class="project-name">
                <br>
                <span class="title">{{ title }}</span> <span class="subtitle">{{ subtitle }}</span>
                <br>
                <br>
            </div>
            <div class="project-body">
                {{ body }}
            </div>
            <br>

            <div v-if="!mdBreakpoint" class="tools">
                <span class="label">Tools used:</span>
                <div v-for="tool in tools" :key="tool.index">
                    <div class="tool">
                        {{ tool }}
                    </div>
                </div>
            </div>

            <div v-if="mdBreakpoint" class="tools">
                <span class="label">Tools used:</span>
                <div v-for="tool in mobileTools" :key="tool.index">
                    <div class="tool">
                        {{ tool }}
                    </div>
                </div>
            </div>

            <div v-if="github" class="github">
                <a :href="github" target="_blank" rel="noopener noreferrer">Github</a>
            </div>
            <div v-if="itchio" class="itchio">
                <a :href="itchio" target="_blank" rel="noopener noreferrer">itch.io</a>
            </div>
        </div>
        <!-- Project image preview -->
        <div v-if="image" class="pic">
            <img :src="getImgUrl(image)" :alt="imageAlt">
        </div>
    </div>
</template>

<style scoped>
/* Project card wrapper */
.project-card {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 100px;
    border-bottom: 5px solid transparent;
    transition-duration: 300ms;
    transition-timing-function: ease-in-out;
}

.project-card:hover {
    transform: translate(0px, -2px);
    border-bottom: 5px solid darkcyan;
}

@media all and (max-width: 1200px) {
    .project-card {
        flex-direction: column-reverse;
        background-color: white;
        border-radius: 1%;
        padding: 30px;
    }
}


/* Written content//info */
.info {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    text-align: justify;
    text-justify: inter-word;
}

.yearngrade {
    display: flex;
    justify-content: space-between;
    color: darkcyan;
    font-weight: bold;
    margin-right: 10px;
    margin-bottom: 5px;
}

.project-name > .title {
    font-size: 25px;
    font-weight: bold;
}

.project-name > .subtitle {
    color: #39455C;
    font-size: 18px;
    font-weight: bold;
}


/* List of project tools */
.tools {
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: center;
}

.tools > .label {
    font-weight: bold;
}

.tool {
    color: lightcyan;
    background-color: darkcyan;
    border: 1px solid darkcyan;
    border-radius: 0.375rem;
    margin-left: 10px;
    padding: 2px 8px 2px 8px;
    margin-bottom: 5px;
}

@media all and (max-width: 1200px) {
    .tools > .label {
        display: none;
    }

    .tool {
        margin-left: 0px;
        margin-inline: 3px;
    }
}

.github {
    margin-top: 15px;
    margin-bottom: 15px;
}

.github > a {
    color: #2c3e50;
    font-weight: bold;
    text-decoration: none;
    background-color: lightseagreen;
    border: 1px solid transparent;
    border-radius: 0.375rem;
    padding: 2px 8px 2px 8px;
    transition-duration: 300ms;
    transition-timing-function: ease-in-out;
}

.github > a:hover {
    background-color: darkseagreen;
}

@media all and (max-width: 1200px) {
    .github {
        margin-top: 25px;
        margin-left: 3px;
        margin-bottom: 0px;
    }
}


/* Project thumbnail */
.pic > img {
    width: 30em;
    height: auto;
    margin-left: 10px;
    overflow: hidden;
}

@media all and (max-width: 1200px) {
    .pic {
    display: flex;
    justify-content: center;
    }

    .pic > img {
        width: 90%;
        margin-left: 0px;
        margin-inline: 10px;
        margin-bottom: 20px;
    }
}


/* itchio */
.itchio {
    margin-top: 15px;
    margin-bottom: 15px;
}

.itchio > a {
    color: whitesmoke;
    font-weight: bold;
    text-decoration: none;
    background-color: lightcoral;
    border: 1px solid transparent;
    border-radius: 0.375rem;
    padding: 2px 8px 2px 8px;
    transition-duration: 300ms;
    transition-timing-function: ease-in-out;
}

.itchio > a:hover {
    background-color: coral;
}

@media all and (max-width: 1200px) {
    .itchio {
        margin-top: 25px;
        margin-left: 3px;
        margin-bottom: 0px;
    }
}
</style>
