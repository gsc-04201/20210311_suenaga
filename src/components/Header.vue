<template>
  <div id="header">
    <input type="text" v-model="postcode">
      <button @click="addressBtn">住所自動入力</button>
      <p>Address：{{ address }}</p>
  </div>
</template>

<script>
import axios from "axios"
let url = 'https://apis.postcode-jp.com/api/v4/postcodes/';
let key = '?apiKey= Z45vTswxQiHHvKp1oPxiy5wi8kUvQmyGVdN6EYW';
export default {
  data() {
    return {
      postcode: "2790031",
      address: ""
    }
  }, 
  methods: {
    async addressBtn() {
      const address = await axios.get( url + this.postcode + key);
      console.log(address.data[0].allAddress);
      this.address = (address.data[0].allAddress);
    }
  }
};
</script>

