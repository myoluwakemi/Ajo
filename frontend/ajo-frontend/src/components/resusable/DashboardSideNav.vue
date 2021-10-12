<template>
<div>
  <v-tabs vertical hide-slider active-class="tab-active" background-color="transparent">
    <v-tab class="font-weight-bold" v-for="menu in tabMenu" :key="menu.id" :to="menu.route" :exact="menu.exact">{{ menu.name}}</v-tab>
  </v-tabs>
</div>
</template>

<script>
export default {
  name: "DashboardSideNav",
  props: {
    tabMenu: {
      type: Array,
      default: function (){
        return[
          {
            id: 1,
            name: "Home",
            exact: true,
          },
        ]
      }
    }
  }
}
</script>

<style scoped>

/*.v-tabs--vertical > .v-tabs-bar .v-tab{*/
/*  !*padding-right: 90px !important;*!*/
/*  !*margin-top: 13px !important;*!*/
/*}*/



</style>