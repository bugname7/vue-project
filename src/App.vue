<template>
  <div>
    <Home :posts="posts" />
  </div>
</template>
<script>
import axios from 'axios'
import Home from './components/home/Home.vue'
export default {
  components: {
    Home
  },
  data () {
    return {
      posts: []
    }
  },
  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/posts').then(response => {
      if (response.status == 200) {
        this.posts = response.data
      } else {
        console.log('hatolik bor', response.status)
      }
    })
  }
}
</script>
