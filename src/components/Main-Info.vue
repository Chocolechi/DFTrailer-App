<template>
  <section class="section">
    <article>
      <h1 class="title has-text-centered">DFTrailers</h1>
      <br />
      <p class="subtitle has-text-centered">
        <i><strong>DFTrailers</strong></i> is a Web Application created for
        people like you who want to see the lastest trailers update.
      </p>
    </article>
    <button class="button is-light m-4 mb-5">
      <router-link to="/add">New Trailer</router-link>
    </button>
  </section>
</template>

<script>
export default {
  name: "MainInfo",
};
</script>
<style scoped>
.box {
  border-radius: 10px;
}
</style>