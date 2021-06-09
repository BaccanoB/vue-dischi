<template>
  <div>
      <div id="load_container">
          <h3>Loading...</h3>
          <i class="fab fa-spotify"></i>
      </div>
  </div>
</template>

<script>
export default {
    name:'Loading'
}
</script>

<style lang="scss" scoped>
    @import '../style/mixins';
    @import '../style/variables';
    div {
        position: relative;
        width: 70%;
        height: calc(100vh - 50px);
        margin: 0 auto;

        #load_container {
            @include flex;
            justify-content: center;
            flex-direction: column;
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            color: $spotify_color;

            h3 {
                margin: 30px 0;
                text-transform: uppercase;
                font-size: 30px;  
            }

            i {
                font-size: 50px;
                animation: rotate .5s linear infinite;
            }
        }
    }

    @keyframes rotate {
        from {
            transform: rotate(0deg);
        }
        to {
            transform: rotate(360deg);
        }
    }

</style>