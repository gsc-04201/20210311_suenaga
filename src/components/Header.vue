<template>
  <form>
    <input type="text" maxlength="8" v-model="zipcode">
      <button @click="addressBtn">住所自動入力</button>
    <br />
    Address：<p>{{addressData}}</p>
  </form>
</template>

<script>
import axios from "axios"
export default {
  data() {
    return {
      zipcode: "",
      addressData: ""
    }
  },
  async created() {
    const item = await axios.get(`https://api.zipaddress.net/?zipcode=`);
  },
  methods: {
    addressBtn() {
      axios.get(item + this.zipcode).then((res) => {
        this.addressData = res.data.results[0];
      });
    }
  }
};
</script>