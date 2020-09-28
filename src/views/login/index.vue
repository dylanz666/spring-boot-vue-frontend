<template>
  <div>
    <el-button type="danger" @click="login">test</el-button>
  </div>
</template>
<script>
import { login } from "@/api/login";

export default {
  data() {
    return {
      username: null,
      password: null,
    };
  },
  created() {},
  methods: {
    login() {
      login(this.username, this.password).then((response) => {
        console.log(123);
      });
    },
  },
};
</script>
