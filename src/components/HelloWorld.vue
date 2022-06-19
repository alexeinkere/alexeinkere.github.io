<template>
  <img :src="results.data.qr" />
</template>


<script>
import axios from 'axios';

export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data() {
    return {
      results: [],
      posts: [],
      errors: []
    }
  },
  async created() {
    const response = await axios.post('https://api.lovense.com/api/lan/getQrCode',
      {
        token: 'Fl33N6u4guzQcbwgJoLY2e9inwSulmfW8s5kkBEgFO/E7+DjSJ8qXFhd92sdjCYv', 
        uid: '11111', 
        uname: 'Alexein_', 
        utoken: '11111',
        v: 2
      })
    
     this.results = response.data
  }
}
</script>