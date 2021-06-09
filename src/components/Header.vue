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
    div {
        @include flex;
        width: 100%;
        height: 50px;
        background-color: #2E3A46;

        img {
            width: 40px;
            margin-left: 10px;
        }
    }
</style>