<template>
  <section>
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
</template>

<script>
import Disk from './Disk.vue';
import axios from 'axios';
export default {
    name:'Main',
    components: {
        Disk
    },
    data:function(){
        return{
            urlApi:'https://flynn.boolean.careers/exercises/api/array/music',
            disks:[]
        }
    },
    created: function(){
        axios
            .get(this.urlApi)
            .then(
                (response)=> {
                    this.disks = response.data.response;
                }
            )
    }
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

            .disk {
                width: calc(100% / 6);
                margin: 15px;
                height: 300px;
                background-color: $spotify_color ;
            }
        }
    }
</style>