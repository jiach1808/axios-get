<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
   
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  created(){
    let url = this.HOST+"01/getData.php";
     this.$axios.get(url)
     .then(res =>{
      console.log(res);
        this.msg =res.data[0].name;
    
     })
     .catch(error =>{
     console.log(error);
     })
  }
}
</script>


<style scoped>

</style>
