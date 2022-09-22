<script setup>
import { reactive } from '@vue/reactivity'
import projectCard from '../cards/projectCard.vue'

const project_list = reactive([
  {
    "id": 1,
    "date": 2022,
    "grade": 100,
    "title": "Enoto",
    "subtitle": "a web-based Markdown editor.",
    "body": `An app for editing Markdown documents that comes with a graphical css-based theme editor, 
    a tool for inserting common Markdown snippets & the ability to export to an array of different file 
    formats such as PDF. The Markdown parser uses the PythonMarkdown API for extended functionality & the 
    theme editor uses a Python module I wrote for generating basic CSS templates.`,
    "image": "enoto",
    "imageAlt": "an image of Enoto with a markdown document open in the editor.",
    "tools": ["Flask", "Tailwind", "PIL", "Heroku"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
  {
    "id": 2,
    "date": 2022,
    "grade": 96,
    "title": "Stocks Web App",
    "subtitle": "../../assets/project-thumbnails/stocks.png",
    "body": `A stock-trading app with real prices fetched from the IEX Cloud Core Data API. Users can
    create an account and login to quote, buy or sell a stock. They can view all their stocks in their 
    account's portfolio & keep track of their actions in the transaction history.  The app's backend is 
    written in Flask and I used Bootstrap's CSS component library for quick frontend development. The databases 
    were designed in the SQlite3 database engine.`,
    "image": "stocks",
    "imageAlt": "an image of the Stocks web app open on the portfolio page.",
    "tools": ["Flask", "Bootstrap", "SQLite 3", "IEX Cloud Core Data API"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
  {
    "id": 3,
    "date": 2022,
    "grade": 100,
    "title": "Photo Filter App",
    "subtitle": "",
    "body": `A program that consists of a few bitmap image processing algorithms written in the C programming 
    language. Including Grayscale, Reflect, Blur & Edge detection filters. It uses a CLI interface and receives 
    input from the user to determine the location of the source image to be manipulated and the file destination 
    for the output. The edge detection filter is my implementation of the Sobel operator algorithm which works by 
    estimating the first derivative of an image by doing a convolution between an input and two special kernels, 
    one to detect vertical edges and one to detect horizontal edges.`,
    "image": "",
    "imageAlt": "an image of the edge detection filter being applied to a bitmap image.",
    "tools": ["C programming language"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
  {
    "id": 4,
    "date": 2022,
    "title": "Benkyou",
    "subtitle": "a productivity web app",
    "body": `a single-page interface web app made in Vue.js for students to improve focus and reward productivity. 
    Use the Pomodoro time management technique to schedule study sessions & breaks. It uses TailwindCSS and Vueuse/motion 
    composables to create designs and animations that are smooth and responsive.`,
    "image": "benkyough",
    "imageAlt": "an image of Benkyou's Pomodoro timer.",
    "tools": ["Vue.js", "Tailwind", "Vercel"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
  {
    "id": 5,
    "date": 2022,
    "title": "Recipe REST API",
    "subtitle": "",
    "body": `This Recipes API helps you store the recipes of your favourite dishes alongside images & extra descriptions. 
    The purpose of this project was to learn and practisebuilding a REST API. I learnt about RESTful API guidelines, HTTP 
    requests & status codes, testing API endpoints with a REST Client (Postman & SwaggerUI), and Docker (Container, Image, 
    Deploying on Docker Hub).I used FastAPI to build this project, SwaggerUI for the documentation website & Docker.`,
    "image": "docs_screenshot",
    "imageAlt": "an image of the Recipe API Swagger docs site.",
    "tools": ["FastAPI", "Pydantic", "Docker"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
  {
    "id": 6,
    "date": 2022,
    "title": "Portfolio Website",
    "subtitle": "",
    "body": `UHUAHSUDYHASHD`,
    "image": "",
    "imageAlt": "an image of my portfolio website.",
    "tools": ["Vue.js", "Sass", "Github Pages"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
  {
    "id": 7,
    "date": 2020,
    "title": "Spoderbirb",
    "subtitle": "minimalist 2D action shooter",
    "body": `Rank #141 overall and #99 in audio in #FFS2020 Game Jam. Spoderbirb is an arcade-style game written in GML Code.
    Pixel art & animations done in Piskel.Created the website for the game with itch.io and published the game there.`,
    "image": "spoderbirb",
    "imageAlt": "an image of spoderbirb's thumbnail.",
    "tools": ["GML Code"],
    "github": "https://github.com/tsdenouden/enoto-markdown"
  },
])
</script>

<template>
    <div class="projects">
        <div v-for="proj in project_list" :key="proj.id">
        <projectCard :year="proj.date" :grade="proj.grade" :title="proj.title" :subtitle="proj.subtitle" :body="proj.body"
        :image="proj.image" :imageAlt="proj.imageAlt" :tools="proj.tools" :github="proj.github" />
        </div>
    </div>
</template>