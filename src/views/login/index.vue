<template>
  <div>
    <el-button type="success">Element UI button 1</el-button>
    <el-button type="danger" @click="sayHello">{{ buttonText }}</el-button>
  </div>
</template>

<script>
export default {
  name: "login",
  data() {
    return {
      buttonText: "Element UI button 2",
    };
  },
  created() {
    console.log("This is vue project!");
  },
  methods: {
    sayHello() {
      alert("Hello dylanz!");
    },
  },
};
</script>

<style>
</style>
