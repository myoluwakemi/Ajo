<template>
  <v-app>
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
.card-table{
  cursor: pointer;
}
.v-overlay__scrim{
  background-color:#03a84e !important;
  opacity: 0.47;
  border-color: #003D67 !important;
  //will-change: initial !important;
}
//.card-table {
//
//  .v-data-table > .v-data-table__wrapper > table > tbody > tr > td, .v-data-table > .v-data-table__wrapper > table > thead > tr > td, .v-data-table > .v-data-table__wrapper > table > tfoot > tr > td {
//    border-bottom: none !important;
//  }
//  .theme--light.v-data-table .v-data-table__empty-wrapper {
//    color: black;
//  }
//  .v-data-table__empty-wrapper {
//    text-align: center;
//    font-weight: bold;
//  }
//  .v-data-footer {
//    border-top: 1px #D0DCE4 solid;
//    border-bottom: none !important;
//    border-radius: 3px;
//    box-sizing: border-box;
//    margin-top: 9px !important;
//    font-family: "DM Sans" !important;
//
//    @media (max-width: 600px) {
//      .v-data-footer__select  {
//        display: none;
//      }
//    }
//
//
//  }
//  .v-data-footer__select {
//    font-family: "DM Sans" !important;
//    font-size: 14px !important;
//
//
//
//  }
//  .v-data-footer__select .v-select__selections .v-select__selection--comma {
//    font-family: "DM Sans" !important;
//    font-size: 13px !important;
//  }
//  .v-data-footer__pagination{
//    font-family: "DM Sans" !important;
//    font-size: 13px !important;
//  }
//  .v-data-table-header {
//    border-bottom: 1px #D0DCE4 solid;
//    border-radius: 5px !important;
//
//  }
//  .tr {
//    font-family: "DM Sans" !important;
//  }
//  .v-data-table-header {
//    font-family: "DM Sans" !important;
//
//  }
//}

</style>
