<template>
  <section class="mt-5">
    <button class="button is-light m-4 mb-5">
      <router-link to="/">Go Back Home</router-link>
    </button>
    <div class="title">
      <h1 class="has-text-centered">Edit Trailer</h1>
    </div>
    <div class="container box">
      <form>
        <b-field label="Title" :label-position="labelPosition">
          <input type="text" class="input" v-model="form.titulo" />
        </b-field>

        <b-field label="Director" :label-position="labelPosition">
          <input type="text" class="input" v-model="form.director" />
        </b-field>

        <b-field label="Review" :label-position="labelPosition">
          <textarea
            name=""
            id=""
            rows="5"
            class="textarea"
            v-model="form.reseña"
          ></textarea>
        </b-field>

        <b-field label="Trailer Route" :label-position="labelPosition">
          <input
            type="text"
            class="input"
            placeholder="youtube.com/embed/TrailerUrl"
            v-model="form.rutaTrailer"
          />
        </b-field>
        <b-field label="Main Actor" :label-position="labelPosition">
          <input type="text" class="input" v-model="form.actores" />
        </b-field>

        <b-field label="Release Date" :label-position="labelPosition">
          <input
            type=""
            class="input"
            rounded
            icon="calendar-today"
            v-model="form.año"
          />
        </b-field>
        <div class="buttons">
          <button
            type="button"
            class="button is-warning is-light"
            v-on:click="edit()"
          >
            <i class="fas fa-toolbox"></i><strong>Edit</strong>
          </button>
          <button
            type="button"
            class="button is-danger is-light"
            v-on:click="deleteT()"
          >
            <i class="fas fa-trash-alt"></i><strong>Delete</strong>
          </button>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
import axios from "axios";

export default {
  name: "EditItem",
  data() {
    return {
      labelPosition: "on-border",
      form: {
        id: "",
        titulo: "",
        director: "",
        reseña: "",
        rutaTrailer: "",
        actores: "",
        año: "",
        token: "",
      },
    };
  },
  methods: {
    edit() {
      axios
        .patch(
          "http://www.trailerbydavinci.somee.com/api/trailer/" + this.form.id,
          this.form,
          {
            headers: {
              Authorization: "Bearer " + this.form.token,
            },
          }
        )
        .then(
          this.$router.push("/")
        )
        
    },
    deleteT() {
      axios
        .delete("http://www.trailerbydavinci.somee.com/api/trailer/"+this.form.id,  {
            headers: {
              Authorization: "Bearer " + this.form.token,
            },
          })
        .then(
          this.$router.push("/")
        )
    },
  },
  mounted: function () {
    this.form.id = this.$route.params.id;
    // console.log(this.form.itemId);
    axios
      .get("http://www.trailerbydavinci.somee.com/api/trailer/" + this.form.id)
      .then((data) => {
        this.form.id = data.data.id;
        this.form.titulo = data.data.titulo;
        this.form.director = data.data.director;
        this.form.reseña = data.data.reseña;
        this.form.rutaTrailer = data.data.rutaTrailer;
        this.form.actores = data.data.actores;
        this.form.año = data.data.año;
        this.form.token = localStorage.token;
        console.log(localStorage.token);
      });
  },
};
</script>
