<template>
  <section class="box mt-6">
    <button class="button is-light m-4 mb-5">
      <router-link to="/">Go Back Home</router-link>
    </button>
    <h1 class="has-text-centered is-size-2 mb-6">Login</h1>
    <form action="" v-on:submit.prevent="login">
      <b-field label="Username" :label-position="labelPosition">
        <b-input maxlength="30" v-model="username"></b-input>
      </b-field>

      <b-field label="Password" :label-position="labelPosition">
        <b-input type="password" maxlength="30" v-model="password"></b-input>
      </b-field>
      <input
        class="button is-fullwidth is-success"
        type="submit"
        value="Log In"
      />
    </form>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "LoginApp",
  data() {
    return {
      labelPosition: "on-border",
      username: "",
      password: "",
    };
  },
  methods: {
    login() {
      let auth = {
        username: this.username,
        password: this.password,
      };
      axios
        .post("http://www.trailerbydavinci.somee.com/api/user/login", auth)
        .then((data) => {
          if (data.request.statusText == "OK") {
            localStorage.token = data.data.token;
            // console.log(data)
            // console.log(data.data.token)
            this.$router.push('/');
          }
          
        });
    },
  },
};
</script>