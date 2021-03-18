<template>
  <form>
    <input type="text" v-model="postcode">
      <button @click="addressBtn">住所自動入力</button>
      <p>Address：{{ address }}</p>
  </form>
</template>

<script>
// import axios from "axios"
export default {
  data() {
    return {
      postcode: "2790031",
      address: ""
    }
  }, 
  methods: {
     addressBtn() {
      console.log("hello");
      // const addressData = axios.get('https://apis.postcode-jp.com/api/v4/postcodes/2790031?apiKey= Z45vTswxQiHHvKp1oPxiy5wi8kUvQmyGVdN6EYW').then((res) => console.log(res));
      // const json = JSON.stringify(addressData);
      // console.log(addressData);
      // console.log(json);
      // return this.address = addressData;
    }
  }
};
</script>

  //   methods: {
  //   addressBtn() {
  //     console.log('addressBtn')
  //     axios.get('https://api.zipaddress.net/?zipcode=' + this.zipcode).then((res) => {
  //       console.log(res)
  //     // this.addressData = res.data.results[0];
  //     });
  //   }
  // }
  
