<template>
  <div>
    <Home :posts="posts" />
    <About :comment="comment" />
  </div>
</template>
<script>
import axios from 'axios'
import Home from './components/home/Home.vue'
import About from './components/about/About.vue'
export default {
  components: {
    Home,
    About
  },
  data () {
    return {
      posts: [],
      comment: []
    }
  },
  mounted () {
    axios.get('https://jsonplaceholder.typicode.com/posts').then(response => {
      if (response.status == 200) {
        this.posts = response.data
      } else {
        console.log('hatolik bor', response.status)
      }
    }),
      axios
        .get('https://jsonplaceholder.typicode.com/comments')
        .then(response => {
          if (response.status == 200) {
            this.comment = response.data
          } else {
            console.log('error bor ', response.status)
          }
        })
  }
}
</script>
