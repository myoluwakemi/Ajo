<template>
  <v-app>
    <v-app-bar
      app
      color="primary"

    >
      <div class="d-flex align-center">
        <v-btn to="/dashboard" color="#fffff" >
          <span>Itedo-Anu</span>
        </v-btn>

      </div>

      <v-spacer></v-spacer>

     <span style="color: #fff">Logout</span>
    </v-app-bar>

    <v-main>
      <router-view/>
    </v-main>
  </v-app>
</template>

<script>

export default {
  name: 'App',

  data: () => ({
    //
  }),
};
</script>
<style lang="scss">
*{
  font-family: "DM Sans", serif;
}

</style>
