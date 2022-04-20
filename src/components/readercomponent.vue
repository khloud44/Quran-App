<template>
    <div class="container">
        <div class="row d-flex ">
            <div class="col-md-4" v-for="reader in readers" :key="reader.id">
                <div class="bg-light d-flex justify-content-between align-items-center p-4 m-2 rounded-pill content" v-if="reader.surasData != null">
                    <p  @click="getselecttedReader(reader.surasData)" >القارئ : {{reader.name}} </p>
                    <p class="mt-2"><ion-icon :id="'id'+reader.id" name="heart" @click="addToFavorite(reader)"></ion-icon></p>
                </div>
            </div>
        </div>
    </div>
</template>
    
<script>
export default {
    data:()=>({
        readers:[],
        selecttedReader:'',
        myFavoriteReaders:[],
    }),
    async created(){
        const res = await fetch("https://qurani-api.herokuapp.com/api/reciters");
        this.readers =await res.json();
    },
    methods:{
        getselecttedReader(data){
            this.selecttedReader=data;
            this.$emit('selectedReader',data);
        },
        addToFavorite(reader){
            this.myFavoriteReaders.push(reader);
            console.log(this.myFavoriteReaders);
            document.querySelector(`#id${reader.id}`).classList.add('favorite'); 
        }
    },
    emits:[
        'selectedReader',
    ]
}
</script>
<style scoped>
ion-icon{
    padding:5px;
    /* background-color:; */
    border-radius: 50%;
    color:rgb(172, 164, 164);
    cursor: pointer;
    transition: .5s;
    
}
ion-icon:hover{
    background-color:rgb(238, 230, 230);
    color:rgba(252, 0, 0, 0.836);

}
.favorite{
    background-color:rgb(238, 230, 230);
    color:rgba(252, 0, 0, 0.836);
}
.content{
    transition: .5s;  
}
.content:hover{
    box-shadow: 2px 7px 5px #ccc;
    cursor: pointer;

}
</style>
