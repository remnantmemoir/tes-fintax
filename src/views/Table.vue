<template>
  <div>
    <navbar />
    <table class="table mt-5">
      <thead>
        <tr>
          <th scope="col">No.</th>
          <th scope="col">Email</th>
          <th scope="col">First Name</th>
          <th scope="col">Last Name</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(user, i) in users" :key="user.id">
          <th scope="row">{{ ++i }}</th>
          <td>{{ user.email }}</td>
          <td>{{ user.first_name }}</td>
          <td>{{ user.last_name }}</td>
        </tr>
      </tbody>
    </table>

  </div>
</template>

<script>
import Navbar from "../components/Navbar.vue";
import axios from "axios";


export default {
  components: {
    navbar: Navbar,
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
      .get("https://reqres.in/api/users?pages=2")
      .then((response) => this.setUsers(response.data.data))
      .catch((error) => console.log("Gagal : ", error));
  },
};
</script>