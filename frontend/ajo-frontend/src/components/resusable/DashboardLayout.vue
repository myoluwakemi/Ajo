<template>
  <div>
    <slot name="header"></slot>
      <v-row  no-gutters style="margin-top: 55px" class="pa-2  ">
        <v-col cols="3" class="side-nav" >
          <slot name="side-nav"></slot>
        </v-col>
        <v-col sm="12" md="9">
          <div class="dashboard-content pr-4">
          <slot name="main-content"/>
          </div>
        </v-col>

      </v-row>
    <BottomNav/>


  </div>

</template>

<script>
import BottomNav from "./BottomNav";
export default {
  name: "DashboardLayout",
  components: {BottomNav}
}
</script>

<style scoped lang="scss">
.side-nav{
  @media (max-width: 768px) {
    display: none;
  }
}

</style>