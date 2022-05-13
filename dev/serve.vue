<script>
import Vue from 'vue';
import KylePasswordPad from '@/kyle-password-pad.vue';

export default Vue.extend({
  name: 'ServeDev',
  components: {
    KylePasswordPad
  }
});
</script>

<template>
  <div id="app">
    <kyle-password-pad />
  </div>
</template>
