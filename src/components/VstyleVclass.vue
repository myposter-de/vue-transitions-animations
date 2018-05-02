<template>
  <div class="example">
    <button @click.prevent="toggleStyle()">
      Toggle Style
    </button>
    <button @click.prevent="toggleClass()">
      Toggle Class
    </button>
    <div
      :style="boldStyle"
      class="title"
    >
      Style
    </div>
    <div
      :class="{'underlined': underlined}"
      class="title"
    >
      Class
    </div>
  </div>
</template>

<script>
export default {
  name: 'VstyleVclass',
  data() {
    return {
      bold: false,
      underlined: false,
    };
  },
  computed: {
    boldStyle() {
      return {
        'font-weight': this.bold ? 'bold' : 'normal',
      };
    },
  },
  methods: {
    toggleStyle() {
      this.bold = !this.bold;
    },
    toggleClass() {
      this.underlined = !this.underlined;
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

.underlined {
  text-decoration: underline;
}
</style>
