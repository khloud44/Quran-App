<template>
    <div class="container">
        <div class="row d-flex ">
            <div class="col-md-4" v-for="sura in suras" :key="sura.id">
                <div class="bg-light d-flex justify-content-between align-items-center p-4 m-2 rounded-pill content">
                    <p>{{sura.name}} </p>
                    <ion-icon name="play-circle-outline" :id="'play'+sura.id" @click="setSound(sura)"></ion-icon>
                    <ion-icon name="stop-circle-outline" :id="'stop'+sura.id" class="stop d-none"></ion-icon>
                </div>
            </div>
        </div>
        <div class="row">
            <div class="col-md-12">
                <audio :src="audioSrc" controls autoplay v-if="audioSrc" class="w-100"></audio>
            </div>
        </div>
    </div>
    
</template>

<script>
export default {
    data:()=>({
       audioSrc:'',
       audioPlated:false,
    }),
    methods:{
        setSound(sura){
            this.audioSrc=sura.url;
            this.audioPlated=true
            let stopIcon = document.querySelectorAll('.stop');
            for(let i =0 ; i< stopIcon.length ; i++){
                stopIcon[i].classList.remove('stop'); 
                stopIcon[i].classList.add('d-none'); 
                
            };
            let playIcon = document.querySelectorAll('.play');
            for(let i =0 ; i< playIcon.length ; i++){
                playIcon[i].classList.remove('play'); 
                
            };
            document.querySelector(`#play${sura.id}`).classList.add('play'); 
            document.querySelector(`#stop${sura.id}`).classList.add('stop'); 
            document.querySelector(`#stop${sura.id}`).classList.remove('d-none'); 
        }
    },
    props:[
        'suras',
    ]
}
</script>
<style scoped>
ion-icon{
    padding:5px;
    border-radius: 50%;
    color:rgb(164, 168, 172);
    cursor: pointer;
    transition: .5s;
    
}
stop-circle-outline{
    background-color:rgb(238, 230, 230);
    color:rgba(252, 0, 21, 0.904);
}
ion-icon:hover{
    background-color:rgb(238, 230, 230);
    color:rgba(0, 160, 252, 0.904);

}
.content{
    transition: .5s;  
}
.content:hover{
    box-shadow: 2px 7px 5px #ccc;
    cursor: pointer;

}
audio{
    position:fixed;
    bottom:0;
    left:0;
    right:0;
    z-index:1000;
}
.play{
    display:none;
}
.stop{
    padding:5px;
    border-radius: 50%;
    cursor: pointer;
    transition: .5s;
    background-color:rgb(238, 230, 230);
    color:rgba(0, 160, 252, 0.904);
}
</style>