<template>
  <div class="wrapper">
    <div class="side-menu">
      <div class="side-menu-top">
        <slot name="top-nav"></slot>
      </div>
      <div class="side-menu-list">
        <slot name="side-menu-list"></slot>
      </div>
    </div>
    <div
        class="main-content"
        :style="{
        left: collapsed ? '3%' : '256px',
      }"
    >
      <div class="main-content-top">
        <slot name="main-content-top"></slot>
      </div>
      <div class="main-content-container">
        <slot name="main-content">I am another slot</slot>
      </div>
    </div>
    <div class="right-nav">
      <div class="right-content-top"></div>
      <div class="right-nav right-content">
        <slot name="right-content">fhfgvkhj</slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "BranchLayout",
  data() {
    return {
      collapsed: false,
    };
  },
  props: {
    wrapper_height: {
      default: "80vh",
    },
    showRightNav: Boolean,
  },
}
</script>

<style scoped lang="scss">
.wrapper {
  height: 80vh;
  width: 95%;
  border-radius: 10px;
  position: relative;
  box-shadow: 0 11.25px 22.5px rgba(130, 130, 130, 0.15);

  .side-menu-top,
  .main-content-top,
  .right-content-top {
    width: 100%;
    height: 53px;
    border-bottom: 0.75px solid rgba(130, 130, 130, 0.15);
  }
  .main-content-top {
    display: flex;
    align-content: center;
    justify-content: center;
  }
  .side-menu {
    position: absolute;
    background: #fff;
    height: 100%;
    border-top-left-radius: 10px;
    border-bottom-left-radius: 10px;
    z-index: 2;
    border-right: 1px solid #f6f6f6;
    transition: all 0.5s ease-in-out;
    max-width: 256px;
    width: 256px;

    .side-menu-list {
      overflow-y: auto;

      height: calc(100% - 50px);
    }
  }
  //::-webkit-scrollbar {
  //  width: 5px;
  //}
  //::-webkit-scrollbar-track {
  //  box-shadow: inset 0 0 5px rgb(255, 255, 255) !important;
  //  border-radius: 5px !important;
  //}
  //
  //::-webkit-scrollbar-thumb {
  //  background: rgb(255, 255, 255) !important;
  //  border-radius: 5px !important;
  //}
  //
  //::-webkit-scrollbar-thumb:hover {
  //  background: #000000 !important;
  //}
  .drawer-toggle {
    width: 20px;
    height: 20px;
    background: #fff;
    position: absolute;
    cursor: pointer;
    top: 50%;
    transition: all 0.8s ease-in-out;
    border-radius: 100%;
    border: 0.75px solid rgba(130, 130, 130, 0.15);
    display: flex;
    align-content: center;
    justify-content: center;
  }

  .main-content {
    position: absolute;
    background: #fff;
    width: calc(100% - 250px);
    height: 100%;
    transition: all 0.5s ease-in-out;
  }
  .main-content-container {
    height: calc(100% - 80px);
    overflow-y: auto;
    overflow-x: hidden;
  }
  .right-nav {
    position: absolute;
    right: 0;
    width: 256px;
    background: #fff;
    border-top-right-radius: 10px;
    border-bottom-right-radius: 10px;
    border-left: 0.75px solid rgba(130, 130, 130, 0.15);
    height: 94.5%;
  }
}

</style>