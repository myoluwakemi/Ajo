<template>
<div>
  <dashboard-layout>
    <template #side-nav>
      <DashboardSideNav/>
    </template>
    <template #main-content>
     <router-view/>
    </template>
  </dashboard-layout>
</div>
</template>

<script>
import DashboardLayout from "../components/resusable/DashboardLayout";
import DashboardSideNav from "../components/resusable/DashboardSideNav";
export default {
  name: "Dashboard",
  components: {DashboardSideNav, DashboardLayout}
}
</script>

<style scoped>

</style>