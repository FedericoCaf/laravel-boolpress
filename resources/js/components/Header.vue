<template>
  <header>
      <nav>
        <ul>
          <li>
            <router-link :to=" {name: 'home'} "> HOME </router-link>
          </li>
          <li>
            <router-link :to=" {name: 'blog'} "> BLOG </router-link>
          </li>
          <li>
            <router-link :to=" {name: 'about'} "> CHI SIAMO </router-link>
          </li>
          <li>
            <router-link :to=" {name: 'contacts'} "> CONTATTI </router-link>
          </li>
         
        </ul>
      </nav>

  </header>
</template>

<script>
export default {
  name: "Header"
}
</script>

<style lang="scss">

header{
  background-color: dodgerblue;
  text-align: center;
  padding: 25px 0;
    ul{
      list-style: none;
        li{
          display: inline-block;
          margin: 0 25px;
          font-size: 17px;
            a{
              color: white;
              text-decoration: none;
                &.active{
                  color: blue;
                }
            }
        }
    }
}

</style>