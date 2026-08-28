<script setup lang="ts">
import { ref } from 'vue'

const mood = ref('')

const moods = ['😊 Glad', '😢 Ledsen', '😡 Arg', '😴 Trött', '😌 Lugn']

</script>

<template>
<h1>Hur känner du dig idag?</h1>

  <button v-for="item in moods" :key="item" @click="mood = item">
  {{ item }}
</button>

<p v-if="mood">Du känner dig: {{ mood }}</p>

</template>