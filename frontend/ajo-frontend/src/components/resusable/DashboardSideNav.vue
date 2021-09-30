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
.v-tab{
  width: fit-content  !important;
  transition: 0.8s ease-in !important;
  text-transform: capitalize;
 font-style: normal;
  font-size: 14px;
  font-weight: normal;
  line-height: 24px;
  padding-left:0 !important;
}
/*.v-tabs--vertical > .v-tabs-bar .v-tab{*/
/*  !*padding-right: 90px !important;*!*/
/*  !*margin-top: 13px !important;*!*/
/*}*/
.tab-active{
  font-weight: bold;
  color: #008EEF !important;
  background: #F7FCFF;
  border-radius: 64px;
}
.theme--light.v-tabs .v-tab--active:hover::before, .theme--light.v-tabs .v-tab--active::before {
  opacity:0;
}

</style>