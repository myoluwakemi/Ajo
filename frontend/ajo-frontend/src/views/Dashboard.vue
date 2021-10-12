<template>
<div>
  <Header/>
  <DashboardLayout>
    <template v-slot:mainContent>
      <DashboardHome/>
    </template>

  </DashboardLayout>
</div>
</template>

<script>
import DashboardLayout from "../components/resusable/DashboardLayout";
import Header from "../components/resusable/Header";
import DashboardHome from "../components/DashboardHome";
export default {
  name: "Dashboard",
  components: {DashboardHome, Header,  DashboardLayout}
}
</script>

<style scoped>

</style>