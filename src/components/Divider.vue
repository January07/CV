<template>
  <div class="divider" v-bind:style="style">
    <div class="divider-item" />
    <div class="divider-icon">
      <i class="fas fa-star" />
    </div>
    <div class="divider-item" />
  </div>
</template>

<script>
export default {
  name: "Divider",

  props: {
    color: {
      type: String,
      required: true
    }
  },

  computed: {
    style() {
      return {
        '--color': this.color
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.divider {
  margin: 1.25rem 0 1.5rem;
  display: flex;
  justify-content: center;
  align-items: center;

  .divider-item {
    background-color: var(--color);
    width: 100%;
    max-width: 7rem;
    height: 0.25rem;
    border-radius: 1rem;
  }

  .divider-icon {
    color: var(--color);
    font-size: 2rem;
    margin: 0 1rem;
  }
}
</style>