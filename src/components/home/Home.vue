<template>
  <div v-for="(data, index) in users" :key="data.id">
    <h2>{{ index + 1 }}-{{ data.email }}</h2>
  </div>
</template>
<script>
export default {
  props: ['users']
}
</script>
