<template>
<div class="container-flued">
    <div id="carouselExampleFade" class="carousel slide carousel-fade" data-bs-ride="carousel">
      <div class="carousel-inner h-25">
        <div class="carousel-item active">
          <img src="../assets/1.jpeg" class="d-block w-100 vh-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="../assets/2.jpeg" class="d-block w-100 vh-100" alt="...">
        </div>
        <div class="carousel-item">
          <img src="../assets/3.jpeg" class="d-block w-100 vh-100" alt="...">
        </div>
      </div>
      <button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleFade" data-bs-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
</div>
</template>
<style scoped>
img{
  height:100vh;
}
.container-flued{
  overflow: hidden;
}
</style>