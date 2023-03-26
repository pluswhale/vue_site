<template>
  <div class="mainpage">
    <Header/>
    mainpage  
  </div>
</template>

<script>
import Header from '@/components/Header/Header'

export default {
  name: 'MainPageView',
  components: {
    Header
  }
}
</script>



<style>

.mainpage {
  min-height: 100vh;

}

</style>
