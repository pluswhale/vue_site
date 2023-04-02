<template>
  <div class="mainpage">
    <Header/>
    <section-welcome/>
    <section-two/>
      
  </div>
</template>

<script>
import Header from '@/components/Header/Header'
import SectionWelcome from '@/sections/SectionWelcome.vue';
import SectionTwo from '@/sections/SectionTwo.vue';

export default {
  name: 'MainPageView',
  components: {
    Header, SectionWelcome, SectionTwo
  }
}
</script>



<style>

.mainpage {
  min-height: 100vh;

}

</style>
