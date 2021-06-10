<template>
  <div id="select_bar">
          <select
           v-model="searchGenre"
           @change="$emit('search', searchGenre)"
           name="genre" id="genre"> 
              <option value="">All genres</option>
              <option value="Rock">Rock</option>
              <option value="Pop">Pop</option>
              <option value="Jazz">Jazz</option>
              <option value="Metal">Metal</option>
          </select>
      </div>
</template>

<script>
export default {
    name:'Searching',
    data: function() {
         return {
            searchGenre: '',
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
     #select_bar {
            width: 100%;
            text-align: right;

            select {
                margin: 20px;
                padding: 5px;
                background-color:#1ED760;
                text-transform: $text_style;
                font-weight: 700;
                color: #2E3A46;
                border-radius: 5px;

                option {
                    color: #2E3A46;
                    text-transform: $text_style;
                }
            }
        }
</style>