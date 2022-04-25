<template>
  <div class="columns is-multiline is-mobile is-variable">
    <div class="column card m-5" v-for="item in trailer" :key="item.id">
      <div class="card-image">
        <iframe
          :src="item.rutaTrailer"
          style="height: 400px; width: 100%"
          title="Iframe Example"
        ></iframe>
      </div>
      <div class="card-content">
        <div class="media">
          <div class="media-content">
            <p class="title is-4">{{ item.titulo }}</p>
            <p class="subtitle is-6"></p>
          </div>
        </div>

        <div class="content">
          <strong>Review:</strong> {{ item.reseña }}
          <br />
          <br />
          <p><strong>Director: </strong>{{ item.director }}</p>
          <time><strong>Date Realeased: </strong> {{ item.año }}</time>
        </div>
        <button class="button is-light is-link is-fullwidth mr-5" style="margin-bottom:0; padding-bottom:0;" v-on:click="editTrailer(item.id)">
          <i class="fas fa-toolbox"> <strong>Edit</strong></i>
        </button>


      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "TrailerList",
  data() {
    return {
      trailer: null,
    };
  },
  mounted() {
    this.getTrailers();
  },

  methods: {
    addTrailer() {
      // const trailer = {
      //     titulo: "",
    },
    getTrailers() {
      axios
        .get("http://www.trailerbydavinci.somee.com/api/trailer")
        .then((response) => {
          // console.log(response);
          this.trailer = response.data;
        });
    },
    editTrailer(id){
      this.$router.push('/edit/' + id)
    },
    created: function () {},
  },
};
</script>


<style scoped>
.card {
  min-width: 500px;
}
</style>