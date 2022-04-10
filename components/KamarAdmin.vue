<template>
  <div id="app" style="margin-top:2000px">
    <h1 id="room">kamar saha</h1>
    <div v-for="(kamar,i) in info" :key="i" >
      {{ kamar.name }}
    </div>
    
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'KeteranganKamar',
  data() {
    return {
      info: null,
    }
  },
  mounted() {
    axios
      .get('http://localhost:5000/services/kamar')
      // .then(response => { console.log(response.data) })
      .then((response) => (this.info = response.data.result))
  },
}
</script>
