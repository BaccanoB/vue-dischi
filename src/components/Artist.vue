<template>
    <div>
        <select
        v-model="searchArtist"
        @change="$emit('search', searchArtist)"
        name="artist" id="artist"> 
            <option value="">All Artist</option>
            <option value="Bon Jovi">Bon Jovi</option>
            <option value="Queen">Queen</option>
            <option value="Sting">Sting</option>
            <option value="Steve Gadd Band">Steve Gadd Band</option>
            <option value="Iron Maiden">Iron Maiden</option>
            <option value="Eric Clapton">Eric Clapton</option>
            <option value="Deep Purple">Deep Purple</option>
            <option value="Metallica">Metallica</option>
            <option value="Dave Weckl">Dave Weckl</option>
            <option value="Michael Jacjson">Michael Jacjson</option>
    </select>
    </div>
</template>

<script>
export default {
    name:'Artist',
     data: function() {
         return {
            searchArtist:''
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';
    div {
        width: 100%;
        text-align: right;

        select {
            margin: 0 20px;
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