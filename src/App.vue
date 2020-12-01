<template>
  <div class="wallet">
    <h2>Wallet</h2>
    <form>
      <input v-model="user.name" type="text" placeholder="name" />
      <input v-model="user.mnemonic" type="text" placeholder="mnemonic" />
      <input @click.prevent="onSubmit" type="submit" />
    </form>
    <div v-if="identifyScreen" class="identification">
      <h4>Your Name is: {{ user.name }}</h4>
      <h4>Your mnemonic is:{{ user.mnemonic }}</h4>
      <h4>Your Public Address is:</h4>
      <h4>Your Balance is:</h4>
      <div class="express">
        <form>
          <input
            v-model="expression"
            type="text"
            placeholder="What's on your Mind?"
          />
          <input @click.prevent="expressMe" type="submit" />
        </form>
        <div v-if="express" class="statement">
          <h4>Your Statement is: {{ expression }}</h4>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import Computer from "bitcoin-computer";
// const computer = new Computer({
//   seed: "",
//   chain: "BSV",
//   network: "testnet",
// });
import { v4 as uuidv4 } from "uuid";

export default {
  name: "App",
  data() {
    return {
      user: { name: "", mnemonic: "", id: uuidv4() },
      expression: "",
      expressions: [],
      identifyScreen: false,
      express: false,
    };
  },
  methods: {
    onSubmit() {
      this.identifyScreen = true;
      console.log(this.user.name, this.user.mnemonic, this.user.id);
    },
    expressMe() {
      this.express = true;
      this.expressions.push(this.expression);
      console.log(this.expressions);
      console.log(this.expression);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
  