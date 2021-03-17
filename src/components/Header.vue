<template>
  <form>
    <input type="text" v-model="postcode">
      <button @click="addressBtn">住所自動入力</button>
      <p>Address：{{ address }}</p>
  </form>
</template>

<script>
import axios from "axios"
let url = 'https://apis.postcode-jp.com/api/v4/postcodes/{postcode} \
  -G -v \
  -d "apikey= Z45vTswxQiHHvKp1oPxiy5wi8kUvQmyGVdN6EYW';
export default {
  data() {
    return {
      postcode: "2790031",
      address: ""
    }
  }, 
  methods: {
     addressBtn() {
      const addressData = axios.get(url+ this.postcode).then((res) => console.log(res));
      console.log(addressData);
      this.address = addressData;
    }
  }
  //   methods: {
  //   addressBtn() {
  //     console.log('addressBtn')
  //     axios.get('https://api.zipaddress.net/?zipcode=' + this.zipcode).then((res) => {
  //       console.log(res)
  //     // this.addressData = res.data.results[0];
  //     });
  //   }
  // }
};
</script>