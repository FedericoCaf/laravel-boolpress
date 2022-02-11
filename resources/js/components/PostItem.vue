<template>

<article>

  <h3>
    <router-link :to=" {name: 'detail', params: {slug: post.slug} } ">  {{post.title }} </router-link>
  </h3>
  
  <p class="data"> {{ formatData }} </p>
  <p> {{ post.content }} </p>

  
</article>

</template>

<script>

export default {
  name: "PostItem",
  props:{
    'post': Object
  },

  computed: {
    formatData(){

      const d = new Date(this.post.created_at);
      let day = d.getDate();
      let month = d.getMonth() + 1;
      const year = d.getFullYear();

      if(day < 10) day = '0' + day;
      if(month < 10) day = '0' + month;

      return `${day} / ${month}   / ${year} `;

    }
  }

}

</script>

<style lang="scss" scoped>

  article{
    h3{
     margin-bottom: 15px;
    }
    p{
      margin: 5px;
    }
    a{
      text-decoration: none;
      color: rgb(43, 39, 39);
    }
  }

</style>