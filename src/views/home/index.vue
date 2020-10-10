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
    <div>
      <el-button @click="logout">Log Out</el-button>
    </div>
  </div>
</template>

<script>
import { getAuth, logout } from "@/api/auth";

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
  methods: {
    logout() {
      logout().then((response) => {
        window.location.href = "/#/login.html";
      });
    },
  },
};
</script>

<style>
</style>
