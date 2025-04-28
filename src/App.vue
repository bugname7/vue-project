<template>
  <div>
    <Home :users="user" />
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
      user: []
    }
  },
  mounted () {
    axios
      .get('https://jsonplaceholder.typicode.com/users')
      .then(response => {
        if (response.status == 200) {
          this.user = response.data
        } else {
          console.log('xatolik bor qayerdadir', response.status)
        }
      })
      .catch(error => {
        console.log(error)
      })
  }
}
</script>
