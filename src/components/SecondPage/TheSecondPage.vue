<template>
  <div class="second__page">
    <h1 class="second__page-text">We are Duo Studio,</h1>
    <div class="second__page-container">
      <div class="second__page-left">
        <h2>a creative collective made to unlock your brand's potential</h2>
      </div>
      <div class="second__page-right">
        <p>
          <strong>
            We weave together bold strategy and creative execution to produce
            thought-provoking digital experiences. We take a highly personalized
            approach to delivering branding, web design, and content marketing
            solutions. Born in the DC area - now serving clients worldwide.
          </strong>
        </p>
        <button class="second__page-about">About Us</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  setup() {
    return {};
  },
  mounted() {
  },
  methods: {
  }
};
</script>

<style lang="scss" scoped>
.second__page {
  min-height: 90vh;
  width: 100%;
  padding: 100px 5vw;
  color: #111;
  border-bottom: 1px solid #111;
  z-index: 9;

  h1.second__page-text {
    font-size: 8vw;
    font-weight: 500;
  }
  .second__page-container {
    position: relative;
    width: 100%;
    height: 60vh;
    display: flex;
    top: 8vh;
    align-items: center;
    justify-content: space-between;

    .second__page-left {
      width: 38%;
      h2 {
        font-size: 3.7vw;
        font-weight: 400;
        text-transform: uppercase;
        line-height: 4vw;
      }
    }
    .second__page-right {
      width: 26%;
      p {
        font-size: 19px;
        font-weight: 300;
        letter-spacing: 0.07em;
      }
      .second__page-about {
        width: 100%;
        border-radius: 50px;
        border: none;
        padding: 4px 0;
        background-color: #edbfff;
        color: #111;
        margin-top: 20px;
      }
    }
  }
}
</style>
