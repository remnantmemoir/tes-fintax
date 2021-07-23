<template>
  <div>
    <b-card no-body class="overflow-hidden" style="max-width: 540px">
      <b-row no-gutters>
        <b-col md="6">
          <b-card-img
            v-bind:src="user.avatar"
            alt="Image"
            class="rounded-0"
          ></b-card-img>
        </b-col>
        <b-col md="6">
          <b-card-body v-bind:title="user.first_name">
            <b-card-text>
              {{user.email}}
            </b-card-text>
          </b-card-body>
        </b-col>
      </b-row>
    </b-card>

  </div>
</template>

<script>
export default {
  name: "card",
  props: ["user"],
};
</script>

<style>
</style>