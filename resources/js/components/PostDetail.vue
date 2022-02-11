<template>
  
 
    <div class="fc-container">
        <h3>
            {{ post.title }}
        </h3>

        <p>
            {{post.content  }}
        </p>

        <!-- <h4> {{ post.category.name }} </h4>
        <h5> {{ post.tags.name }}  </h5> -->

    </div>

  
</template>

<script>
export default {
  name: "PostDetail",

  data(){

    return{

      apiUrl: 'http://127.0.0.1:8000/api/posts/',
      post:{
          title: '',
          content: '',
          category: '',
          tags: [],
      }
    }
  },

 methods:{
   getApi(){
     axios.get(this.apiUrl + this.$route.params.slug)
         .then(res=> {
           this.post = res.data;
           console.log(this.post);
         })
   }
 },

 mounted(){
   this.getApi();
 }




}
</script>

<style lang="scss" scoped>

.fc-container{
  padding-top: 50px;
  max-width: 1200px;
  margin: 0 auto;
     h1{
       margin-bottom: 20px;
     }

}

</style>