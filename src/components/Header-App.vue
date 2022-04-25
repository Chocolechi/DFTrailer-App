<template>
  <b-navbar class="">
    <template #brand>
      <b-navbar-item tag="router-link" :to="{ path: '/' }">
        <img src="../assets/logo.png" />
      </b-navbar-item>
    </template>
    <template #start>
        <b-navbar-item href="/"><i class="fas fa-home"></i> <strong>Home</strong></b-navbar-item>
      <!-- <b-navbar-item href="#"> Documentation </b-navbar-item> -->
      <!-- <b-navbar-dropdown label="Info">
        <b-navbar-item href="#"> About </b-navbar-item>
        <b-navbar-item href="#"> Contact </b-navbar-item>
      </b-navbar-dropdown> -->
    </template>

    <template #end>
      <b-navbar-item tag="div" style="display:;">
        <div class="buttons">
          <a  class="button is-outlined is-ligth">
            <router-link to="/login">
              <strong>Log in</strong>
              <b-icon icon="account"></b-icon>
            </router-link>
          </a>
          <!-- <a v-if="!isNotLogged" class="button is-outlined is-ligth">
            <router-link to="/">
              <strong>LOGOUT</strong>
              <b-icon icon="account"></b-icon>
            </router-link>
          </a> -->
        </div>
      </b-navbar-item>
    </template>
  </b-navbar>
</template>

<script>
  export default {
    name: "HeaderApp",
    methods:{
    },
  };
</script>

<style scoped>

</style>