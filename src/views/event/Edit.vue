<template>
<div id="flashMessage" v-if="Gstore.flashMessage">
  {{Gstore.flashMessage}}
</div>
  <p>Edit the event here</p>
  <button @click="Edit">Edit</button>
</template>

<script>
export default {
  props: ['event'],
  inject:['Gstore'],
  methods:{
    Edit(){
      this.Gstore.flashMessage='your data has been edited';
      setTimeout(()=>{
        this.Gstore.flashMessage=''
      },3000)
      this.$router.push({
        name:'EventDetails',
        params:{id:this.event.id}
      })
    }
  }
}
</script>
<style> 
@keyframes yellowfade {
  from{
    background:yellow;
  }
  to{
    background: transparent;
  }
}
#flashMessage{
  animation-name: yellowfade;
  animation-duration: 3s;
}
</style>
