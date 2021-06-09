<template>
  <section v-if="!loading">
      <div class="container">
          <div
            v-for='(disk,index) in disks'
            :key='index'
            class="disk">
                <Disk
                    :img="disk.poster"
                    :title="disk.title" 
                    :author="disk.author"
                    :year="disk.year"
                />
          </div>
      </div>
  </section>
  <Loading v-else />
</template>

<script>
import Disk from './Disk.vue';
import axios from 'axios';
import Loading from './Loading.vue';
export default {
    name:'Main',
    components: {
        Disk,
        Loading
    },
    data:function(){
        return{
            urlApi:'https://flynn.boolean.careers/exercises/api/array/music',
            disks:[],
            loading: true
        }
    },
    created: function(){
        axios
            .get(this.urlApi)
            .then(
                (response)=> {
                    this.disks = response.data.response;
                    this.loading = false;
                }
            )
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    section {
        width: 100%;
        height: calc(100% - 50px);
        background-color: #1E2D3B ;
        font-family: $main_font;

        .container {
            display: flex;
            flex-wrap: wrap;
            align-items: center;
            justify-content: center;
            width: 75%;
            margin: 0 auto;
            height: 100%;

            .disk {
                width: calc(100% / 6);
                margin: 15px;
                height: 320px;
                background-color: $spotify_color ;
            }
        }
    }
</style>