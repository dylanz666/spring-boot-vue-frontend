<template>
  <div>
    <h1>Wellcome, {{ username }}!</h1>
    <el-select v-model="defaultUserRole">
      <el-option
        v-for="item in userRoles"
        :key="item"
        :label="item"
        :value="item"
      >
      </el-option>
    </el-select>
  </div>
</template>

<script>
import { getAuth } from "@/api/auth";

export default {
  name: "home",
  data() {
    return {
      username: "",
      userRoles: [],
      defaultUserRole: "",
    };
  },
  created() {
    getAuth().then((response) => {
      if (response.code == 200 && response.message == "success") {
        this.username = response.username;
        this.userRoles = response.userRoles;
        this.defaultUserRole = this.userRoles[0];
      }
    });
  },
  methods: {},
};
</script>

<style>
</style>
