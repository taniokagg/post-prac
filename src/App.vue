<template>
  <div id="app">
    <input type="address" v-model="address">
    <button @click="serch">住所自動入力</button>
    <p>Address:{{}}</p>
  </div>
</template>

<script>
import axios from "axios";
export default {
  methods: {
    async serch() {
    const item = await axios.get(`https://apis.postcode-jp.com/api/v4/U5NZRvRIZStqlmUptvesc9x2LP0wiOj11LKjSxW/postcode?allAddress
`);
    console.log(item);
    }
  },
  data() {
    return {
      address: "",
    };
  }
}
</script>
