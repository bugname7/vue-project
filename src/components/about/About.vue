<template>
  <div v-for="(data, index) in comment" :key="data.id">
    <h2 class="bg-gray-200 shadow-2xl">{{ index + 1 }},{{ data.email }}</h2>
  </div>
</template>
<script>
export default {
  props: ['comment']
}
</script>
