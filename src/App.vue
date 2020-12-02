<template>
  <div class="wallet">
    <h2>Wallet#2</h2>
    <form>
      <input v-model="mnemonic" type="text" placeholder="mnemonic" />
      <input @click.prevent="onSubmit" type="submit" />
    </form>
    <form v-if="login">
      <br />
      <input type="text" placeholder="song title" /> <br />
      <input type="text" placeholder="artist" /> <br />
      <input type="text" placeholder="url" /> <br />
      <input type="submit" placeholder="Create Publishing Token" />
    </form>
    <h3>{{}}</h3>
  </div>
</template>

<script>
import Computer from "bitcoin-computer";
// hospital antique tip ghost garage sign siege kit general tunnel tower expand
export default {
  name: "App",
  data() {
    return {
      computer: {},
      // mnemonic: "",
      publicKey: "",
      balance: "",
      login: false,
    };
  },
  methods: {
    onSubmit() {
      this.computer = new Computer({
          seed:
            "hospital antique tip ghost garage sign siege kit general tunnel tower expand",
          chain: "BSV",
          network: "testnet",
        });

      this.login = true;
      // this.publicKey = this.computer.db.wallet.getPublicKey().toString();
      console.log(this.computer);
      // console.log(this.computer.db.wallet.getPublicKey().toString());
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
  

