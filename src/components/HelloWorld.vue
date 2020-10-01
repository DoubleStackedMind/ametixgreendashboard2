<template>
  <div>
    <md-field>
      <label>Type here!</label>
      <md-input v-model="type"></md-input>
      <span class="md-helper-text">Helper text</span>
    </md-field>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  data: () => ({
    initial: "Initial Value",
    type: null,
    withLabel: null,
    inline: null,
    number: null,
    textarea: null,
    autogrow: null,
    disabled: null,
  }),
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
