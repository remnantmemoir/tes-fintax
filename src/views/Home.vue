<template>
  <div class="home">
    <navbar />

    <div id="flex-container">
      <div class="flex-container-dots">
        <span class="dots"></span>
      </div>
      <div class="flex-container-text">
        <h1>I'm</h1>
        <h1>Abbi Kurnia R.K.</h1>
        <h1 style="font-family: 'Mr Dafoe', cursive; font-size: 5rem">
          Web Developer
        </h1>
      </div>
    </div>

    <div class="row">
      <div class="col-6 col-sm-4 md-4 mt-4" v-for="user in users" :key="user.id">
        <card :user="user"/>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "../components/Navbar.vue";
import Card from "../components/Card.vue"
import axios from "axios"

export default {
  name: "Home",
  components: {
    navbar: Navbar,
    card: Card
  },
  data() {
    return {
      users: [],
    };
  },
  methods: {
    setUsers(data) {
      this.users = data;
    },
  },
  mounted() {
    axios
      .get("https://reqres.in/api/users")
      .then((response) => this.setUsers(response.data.data))
      .catch((error) => console.log("Gagal : ", error))
  }, 
};
</script>

<style scoped>
@import url("https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Mr+Dafoe&display=swap");
#flex-container {
  display: flex;
  background-image: linear-gradient(#202020, #2c2c2c, #444);
  max-width: 100%;
  height: 30rem;
  padding: 0px;
}
.flex-container-text {
  flex: 1;
  padding-right: 30px;
  padding-top: 80px;
}
.flex-container-text h1 {
  text-align: right;
  color: white;
  font-family: "Bebas Neue", cursive;
  font-size: 5rem;
}
.flex-container-dots {
  flex: 2;
  padding-right: 30px;
  padding-top: 70px;
}
.dots {
  float: right;
  width: 320px;
  height: 320px;
  clip-path: circle(50% at 100%);
  background: rgb(235, 168, 46);
}
.row{
margin: 0px 0px 25px 0px;
}
</style>