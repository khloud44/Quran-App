<template > 
    <div class="row">
        <div class="col-md-12">
            <div>
                 <navcomponent/>
            </div>
        </div>
    </div> 
    <div class="row g-0">
        <div class="col-md-12">
            <div>
                 <homecomponent/>
            </div>
        </div>
    </div>
    <div class="row ">
        <div class="col-md-12 d-flex justify-content-center">
            <div>
                 <searchcomponent/>
            </div>
        </div>
    </div>
    <div class="row" >
        <div class="col-md-12">
            <readercomponent @selectedReader='sendReader'/>
        </div>
    </div>
    <div class="row">
        <div class="col-md-12">
             <suracomponent :suras="suras"/> 
        </div>
    </div>
</template>

<script>
import readercomponent from "./components/readercomponent.vue"
import homecomponent from "./components/homecomponent.vue"
import navcomponent from "./components/navcomponent.vue" 
import searchcomponent from "./components/searchcomponent.vue"
import suracomponent from "./components/suracomponent.vue"
export default {
    data:()=>({
        suras:''
    }),
    components:{
        readercomponent,
        homecomponent,
        navcomponent,
        searchcomponent,
        suracomponent,
    },
    methods:{
        sendReader(data){
            console.log(data);
            this.suras=data;
        }
    },
    emits:[
       'selectedReader',
    ]
}
</script>

