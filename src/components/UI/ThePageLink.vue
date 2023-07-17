<template>
  <div>
    <h4 class="nav__link">
      <a href="#">
        <slot></slot>
      </a>
    </h4>
  </div>
</template>

<script>
export default {
  setup() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
.nav__link {
  font-size: 14px;
  font-weight: 500;
  text-transform: uppercase;

  a {
    text-decoration: none;
    color: #fff;
  }
}
</style>
