<template>
  <div id="staggered-list-demo">
    <input v-model="query">
    <transition-group
      name="staggered-fade"
      tag="ul"
      v-bind:css="false"
      v-on:before-enter="beforeEnter"
      v-on:enter="enter"
      v-on:leave="leave"
    >
      <li
        v-for="(item, index) in computedList"
        v-bind:key="item.msg"
        v-bind:data-index="index"
      >{{ item.msg }}</li>
    </transition-group>
  </div>
</template>

<script>
import Velocity from 'velocity-animate';

export default {
  el: '#staggered-list-demo',
  name: 'list-transitions',
  data() {
    return {
      query: '',
      list: [
        { msg: 'Test' },
      ],
    };
  },
  computed: {
    computedList() {
      const vm = this;
      return this.list.filter(item =>
        item.msg.toLowerCase().indexOf(vm.query.toLowerCase()) !== -1);
    },
  },
  methods: {
    beforeEnter(el) {
      // eslint-disable-next-line
      el.style.opacity = 0;
      // eslint-disable-next-line
      el.style.height = 0;
    },
    enter(el, done) {
      const delay = el.dataset.index * 150;
      setTimeout(() => {
        Velocity(
          el,
          { opacity: 1, height: '1.6em' },
          { complete: done },
        );
      }, delay);
    },
    leave(el, done) {
      const delay = el.dataset.index * 150;
      setTimeout(() => {
        Velocity(
          el,
          { opacity: 0, height: 0 },
          { complete: done },
        );
      }, delay);
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
