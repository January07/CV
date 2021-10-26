<template>
  <div class="side-menu">
    <a class="menu-item" href="https://www.facebook.com/profile.php?id=100006946336316" target="_blank" style="color: #1877f2">
      <i class="fab fa-facebook animation" />
    </a>
    <a class="menu-item" href="https://github.com/January07" target="_blank" style="color: #24292f">
      <i class="fab fa-github animation" />
    </a>
    <a class="menu-item" href="https://line.me/ti/p/RI1t0XyxYG" target="_blank" style="color: #00b900">
      <i class="fab fa-line animation" />
    </a>
    <a class="menu-item" href="tel:+886-971676017" target="_blank" style="color: #4cd863">
      <i class="fas fa-phone-square-alt animation" />
    </a>
  </div>
  <div class="back-top" v-if="scrollY !== 0" v-on:click="backTop">
    <i class="fas fa-chevron-circle-up" />
  </div>
</template>

<script>
export default {
  name: "Menu",

  data() {
    return {
      scrollY: window.top.scrollY
    }
  },

  mounted() {
    window.addEventListener('scroll', this.changeScrollY)
  },

  methods: {
    changeScrollY() {
      this.scrollY = window.top.scrollY
    },
    backTop() {
      window.scrollTo(0, 0)
    }
  }
}
</script>

<style lang="scss" scoped>
.side-menu {
  width: 47.6px;
  top: 30%;
  right: 0;
  position: fixed;
  display: flex;
  flex-direction: column;
  z-index: 100;

  .menu-item {
    font-size: 1.9rem;
    background-color: $light-gray;
    border: 1px solid white;

    .animation:hover {
      animation-name: shake;
      animation-duration: 0.1s;
      animation-iteration-count: infinite;
      animation-direction: alternate;
    }
  }
}

.back-top {
  right: 2.5%;
  bottom: 7.5%;
  position: fixed;
  font-size: 2.5rem;
  cursor: pointer;
  z-index: 100;
}

@keyframes shake {
  from {
    transform: rotate(-10deg);
  }

  to {
    transform: rotate(10deg);
  }
}
</style>