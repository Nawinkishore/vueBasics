<template>
    <div>
        <div class="w-full h-10 bg-green-300 flex items-center justify-center text-2xl">
            <h1>{{title}}</h1>
            
        </div>
        <button v-if="isClicked==true"
        @click="emitMessage()" 
        >Send message to child</button>
     
    </div>
</template>
<script>
export default{
    data(){
        return{
            isClicked: true,

        }
    },
    props:{
        title:String,
        default:true,
    },
    
    methods:{
        emitMessage(){
            this.$emit('message','hello world');
            
        }
       
    }
}
</script>

