<template>
  <div class="pageMain">
    <slot name="mainContent"></slot>
<!--    <slot name="header"></slot>-->
<!--      <v-row  no-gutters style="margin-top: 55px" class="pa-2  ">-->
<!--        <v-col cols="2" class="side-nav" >-->
<!--          <slot name="side-nav"></slot>-->
<!--        </v-col>-->
<!--        <v-col sm="12" md="10">-->
<!--          <div class="dashboard-content pr-4">-->
<!--          <slot name="main-content"/>-->
<!--          </div>-->
<!--        </v-col>-->

<!--      </v-row>-->
<!--    <BottomNav/>-->


  </div>

</template>

<script>
export default {
  name: "DashboardLayout",
}
</script>

<style scoped lang="scss">
.pageMain{
  margin-top: 4rem;
  padding: 1rem;
  @media(min-width: 780px){
    display: flex;
    justify-content: center;
    padding-top: 5rem;

    flex-direction: column;
    width: 80%;
    margin: 2rem auto;
  }
  //@media(min-width: 1300px){
  //  width: 100%;
  //}
  //@media(min-width: 1301px){
  //}
;
}
.side-nav{
  @media (max-width: 768px) {
    display: none;
  }
}

</style>