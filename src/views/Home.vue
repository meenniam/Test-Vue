<template>
  <div class="home">
    <TestVue></TestVue>

  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from "@/components/HelloWorld.vue";
import TestVue from '@/components/TestVue.vue'

export default {
  name: "home",
  components:{
    TestVue
  }
};
</script>
