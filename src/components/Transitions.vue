<template>
  <div class="example">
    <button @click.prevent="toggleVisibility()">
      Toggle Visibility
    </button>
    <transition name="fade" mode="out-in">
      <p v-if="visible">hello</p>
    </transition>
  </div>
</template>

<script>
export default {
  name: 'transitions',
  data() {
    return {
      visible: true,
    };
  },
  methods: {
    toggleVisibility() {
      this.visible = !this.visible;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$size: 16px;

.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
}

button {
  background-color: #64B587;
  border: none;
  color: white;
  cursor: pointer;
  display: inline-block;
  font-size: $size;
  margin: 10px 0;
  padding: 15px 32px;
  text-align: center;
  text-decoration: none;
}

.example {
  display: flex;
  flex-direction: column;
  margin: 0 auto;
  max-width: 200px;
  width: 100%;
}

.title {
  color: #64B587;
  font-size: $size;
  margin: 10px 0;
}
</style>
