<template>
  <p>Regstration form here</p>
  <button @click="register">register</button>
</template>

<script>
export default {
  props: ['event'],
  inject:['Gstore'],
  methods:{
    register(){
      this.Gstore.flashMessage = 'you are already regsiter for '+this.event.title
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
