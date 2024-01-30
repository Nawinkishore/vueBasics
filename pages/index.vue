<template>
  <div>
   <navbar title="Kishore" @message="sended" />
   <div :class="{'bg-black text-white w-full h-10 flex justify-center items-center ':active}">
    <h1>{{ recieve }}</h1>
   </div>
   <slots>
      <template #body>
        <div>
          hello
        </div>
      </template>
   </slots>
  
  
   
   
  </div>
</template>
<script>
export default{
  data(){
    return{
      recieve:"",
      active:false,
    };
  },
  methods:{
    sended(recieved){
      this.recieve = recieved;
      this.active = true;
     
      },
      
  }
}
</script>
