<template>
  <div>
      <img src="../assets/spotify.png" alt="spotify_logo">
  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
    @import '../style/mixins';
    @import '../style/variables';
    div {
        @include flex;
        width: 100%;
        height: 50px;
        background-color: $spotify_color ;

        img {
            width: 40px;
            margin-left: 10px;
        }
    }
</style>