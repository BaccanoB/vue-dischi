<template>
  <section v-if="!loading">
      <Searching @search="searchingGenre" />
      <Artist @search="searchingGenre"/>
      <div class="container">
          <div
            v-for='(disk,index) in filteredGenre'
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
import Searching from './Searching.vue';
import Artist from './Artist.vue';
export default {
    name:'Main',
    components: {
        Disk,
        Loading,
        Searching,
        Artist
    },
    data:function(){
        return{
            urlApi:'https://flynn.boolean.careers/exercises/api/array/music',
            disks:[],
            loading: true,
            selectGenre: ""
        }
    },
    computed: {
        filteredGenre: function(){
             if(this.selectGenre == "") {
                return this.disks;
            }
            const selectedArray = this.disks.filter(
                (element) => {
                    return element.genre.includes(this.selectGenre) || element.author.includes(this.selectGenre)
                } 
            );
            return selectedArray;
        }
    },
    methods: {
        searchingGenre: function(text){
            this.selectGenre = text;
        },
        searchingArtist: function(text){
            this.selectArtist = text;
        }
    },
    created: function(){
        axios
            .get(this.urlApi)
            .then(
                (response)=> {
                    this.disks = response.data.response;
                    setTimeout(()=>{
                        this.loading = false;
                    },3000)
                }
            )
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/mixins';
    @import '../style/variables.scss';

    section {
        width: 100%;
        height: calc(100% - 50px);
        background-color: #1E2D3B ;
        font-family: $main_font;

        .container {
            @include flex;
            flex-wrap: wrap;
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