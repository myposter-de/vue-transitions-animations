<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div>{{ info }}</div>
    <tabs>
      <tab name="v-show & v-if">
        <VshowVif />
      </tab>
      <tab name="Bind styles or classes">
        <VstyleVclass />
      </tab>
      <tab name="Transitions">
        <Transitions />
      </tab>
    </tabs>
  </div>
</template>

<script>
import VshowVif from './VshowVif';
import VstyleVclass from './VstyleVclass';
import Transitions from './Transitions';

export default {
  name: 'Animations',
  components: {
    VshowVif,
    VstyleVclass,
    Transitions,
  },
  data() {
    return {
      msg: 'Welcome to Vue Animations',
      info: '(with Vue Tab Components)',
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  font-weight: normal;
}
</style>
