<template>
  <div id="app">
    <input type="address" v-model="address">
    <button @click="serch">住所自動入力</button>
    <p>Address:{{showAddress}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      address: "",
    };
  },
    methods: {
      async serch() {
        const item = await axios.get(`https://apis.postcode-jp.com/api/v4/postcodes/${this.address}?apikey=U5NZRvRIZStqlmUptvesc9x2LP0wiOj11LKjSxW`);
        return showAddress = item.data[0].allAdress;
      }
    }
  }
</script>


