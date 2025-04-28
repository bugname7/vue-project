<template>
  <div v-for="(data, index) in posts" :key="data.id">
    <h1>{{ index + 1 }}. {{ data.title }}</h1>
  </div>
</template>
<script>
export default {
  props: ['posts']
}
</script>
