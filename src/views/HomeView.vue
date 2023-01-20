<template>
  <div class="home">
      
   <datatable/>
  </div>
</template>

<script>
import Datatable from '@/components/datatable.vue'
// @ is an alias to /src

export default {
  name: 'HomeView',
  components: {
    Datatable
    
  }
}
</script>
