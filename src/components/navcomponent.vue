<template>
    <nav class="navbar navbar-expand-lg navbar-light bg-light">
  <div class="container-fluid">
    <a class="navbar-brand" href="#">الْقُرْآن الْكَرِيْم<ion-icon name="book"></ion-icon></a>
    
    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
      <span class="navbar-toggler-icon"></span>
    </button>
    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav me-auto mb-2 mb-lg-0">
        <li class="nav-item">
          <a class="nav-link active" aria-current="page" href="#">المشايخ</a>
        </li>
        <li class="nav-item">
          <a class="nav-link" href="#">المفضل</a>
        </li>
        <li class="nav-item">
          <!-- <a class="nav-link" href="#">أخر صوت</a> -->
        </li>
      </ul>
    </div>
  </div>
</nav>
</template>

<script>
export default {
  props:[
    
  ]
}
</script>

<style scoped>
.navbar{
    position:fixed;
    top:0px;
    left:0px;
    right:0px;
    z-index: 1000;
}
ion-icon{
  color:rgb(28, 179, 230);
  font-size:1.8em;
  position:relative;
  top:10px;
  right:5px;
}
</style>