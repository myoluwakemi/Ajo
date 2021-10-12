<template>
  <v-app-bar color="#03a84e" fixed elevation="1" height="68">
    <div  class="d-flex justify-space-between align-center pr-3 pl-3 header" style="width: 100%">
      <div>
        <h3 style="font-size: 23px">Ajo</h3>
      </div>
      <v-spacer></v-spacer>
      <div class="headerLeft">
        <span>Hi, kemi</span>
      </div>
    </div>
  </v-app-bar>

</template>

<script>
export default {
  name: "Header"
}
</script>

<style scoped lang="scss">
.headerLeft{
  display: flex;
  justify-content: center;
  align-items: center;
  span {
    font-size: 14px;
  }
  @media (max-width: 768px) {
    display: none;
  }
}
.header{
  color:  #fdd384
}

</style>