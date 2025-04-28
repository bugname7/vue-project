<template>
  <div>
    <button
      @click="toggleLogin"
      class="bg-black text-red-700 w-1/2 p-4 cursor-pointer"
    >
      {{ loggedIn ? 'Chiqish' : 'Kirish' }}
    </button>
  </div>
</template>

<script>
export default {
  data () {
    return {
      loggedIn: false
    }
  },
  methods: {
    toggleLogin () {
      this.loggedIn = !this.loggedIn
    }
  }
}
</script>
