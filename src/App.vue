<script setup lang="ts">
import { ref } from 'vue'

const mood = ref()

const moods = [
  { name: '😊 Glad', image: '/meme-glad.jpg' },
  { name: '😢 Ledsen', image: '/meme-ledsen.jpg' },
  { name: '😡 Arg', image: '/meme-arg.jpg' },
  { name: '😴 Trött', image: '/meme-trött.gif' },
  { name: '😌 Lugn', image: '/meme-lugn.webp' }
]

const messages ={
  '😊 Glad': 'Vad härligt! 😄',
  '😢 Ledsen': 'Hoppas det känns bättre snart ❤️',
  '😡 Arg': 'Ta ett djupt andetag. 🌿',
  '😴 Trött': 'Dags för lite vila kanske? 😴',
  '😌 Lugn': 'Härligt med lite lugn och ro. 🌿'
}

</script>

<template>  
  <h1>Hur känner du dig idag?</h1>
  <p v-if="mood" class="result">Du känner dig: {{ mood.name }}</p>
  <p v-if="mood" class="message">{{ messages[mood.name] }}</p>

  <div class="mood-buttons">
  <button v-for="item in moods" :key="item.name" @click="mood = item">
    {{ item.name }}
  </button>
</div>

<div v-if="mood">
  <img :src="mood.image" :alt="mood.name">
</div>

</template>