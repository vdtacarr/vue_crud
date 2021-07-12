<template>
  <div >
    
    
    <h3 class="alert alert-danger"> 
    {{msg}}
    </h3>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
