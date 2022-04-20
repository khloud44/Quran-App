<template>
    <form class="d-flex m-3">
        <div class="position-relative">
            <input class="form-control me-2" type="text" placeholder="بحث عن قارئ ..." aria-label="Search">
            <ion-icon name="search"></ion-icon>
        </div>
    </form>
</template>
<style scoped>
ion-icon {
    position:absolute;
    top:6px;
    left:15px;
    color:rgb(163, 159, 159);
} 
input{
    border: 1px solid #999;
    border-radius: 50px;
}
</style>