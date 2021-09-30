<template>
  <div class="button-nav">
    <v-bottom-navigation v-model="value"  fixed color="#008eef">
      <v-btn v-for="(data,i ) in menu" :key="i" :value="data.name" :exact="data.exact" :to="data.route">
        <v-icon>mdi-history</v-icon>
      </v-btn>
    </v-bottom-navigation>
  </div>

</template>

<script>


export default {
  name: "BottomNav",
  data(){
    return{
      value:'',
    }
  },
  props: {
    menu:{
      type: Array,
      default: function () {
        return [

          {
            id: 1,
            name: "Home",
            exact: true,
            icon: history

          },

        ]
      }
    }
  }
}
</script>

<style scoped lang="scss">
.button-nav{
  @media (min-width: 769px) {
    display: none;
  }
}

</style>