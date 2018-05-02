<template>
  <div class="example">
    <button @click.prevent="toggleExistence()">
      Toggle Existence
    </button>
    <button @click.prevent="toggleVisibility()">
      Toggle Visibility
    </button>
    <div
      v-if="exists"
      class="title"
    >
      Exists
    </div>
    <div
      v-show="visible"
      class="title"
    >
      Visible
    </div>
  </div>
</template>

<script>
export default {
  name: 'VshowVif',
  data() {
    return {
      exists: false,
      visible: false,
    };
  },
  methods: {
    toggleExistence() {
      this.exists = !this.exists;
    },
    toggleVisibility() {
      this.visible = !this.visible;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="scss" scoped>
$size: 16px;

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
