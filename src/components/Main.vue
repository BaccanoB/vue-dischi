<template>
  <section>
      <div class="container">
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
          <div class="disc"></div>
      </div>
  </section>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    section {
        width: 100%;
        height: calc(100vh - 50px);
        background-color: #1E2D3B ;

        .container {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            width: 75%;
            margin: 0 auto;
            height: 100%;

            .disc {
                width: calc(100% / 6);
                margin: 15px;
                height: 250px;
                background-color: $spotify_color ;
            }
        }
    }
</style>