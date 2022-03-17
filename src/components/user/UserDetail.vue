<template>
  <div class="container">
    <h3>User Detail Component</h3>
    <hr>
    <p> Kullanıcının ID Bilgisi : {{ $route.params.id }}</p>
    <router-link
      tag="button"
      class="btn btn-primary"
      :to="navigationLink">Kullanıcıyı Düzenle</router-link>
  </div>
</template>
<script>
  export default {
    data(){
      return {
        navigationLink : {
          name : 'userEdit',
          params : { id : this.$route.params.id },
          query : {name : 'ardan', lastName : 'sisman'},
          hash : '#data'
        }
      }
    },
    beforeRouteEnter(to, from, next){
      console.log("Component Seviyesinde Kontrol!!!");
      next();
    }
  }
</script>
