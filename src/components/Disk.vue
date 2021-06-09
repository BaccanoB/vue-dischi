<template>
  <div>
    <div id="img_container">
      <img :src="img" alt="">
    </div>
    <h2>{{ title }}</h2>
    <p>{{ author }}</p>
    <p>{{ year }}</p>
  </div>
</template>

<script>
export default {
    name: 'SingleDisk',
    props:{
      img:String,
      title:String,
      author:String,
      year:String
    }
}
</script>

<style lang="scss" scoped>

div{
  text-align: center;

  #img_container {
    width: 100%;
    height: 100%;
    text-align: center;
    padding:20px 0 ;
    img {
      width: 80%;
    }
  }

  h2 {
    font-size: 15px;
    text-transform: uppercase;
    color: white;
  }

  p {
    color: #71706F;
  }
}


</style>