<script setup lang="ts">
defineProps<{
  post: {
    title: string
    subtitle: string
    tags: string
  }
}>()
</script>

<template>
  <div>
    <pre>
    {{ post }}
    </pre>
    <h2>
      {{ post.title }}
    </h2>
    <p>
      {{ post.subtitle }}
    </p>
    <ul>
      <li v-for="(tag, index) in post.tags" :key="index">
        {{ tag }}
      </li>
    </ul>
  </div>
</template>
