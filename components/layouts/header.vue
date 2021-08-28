<template>
  <div class="items-center flex justify-between w-full" id="header">
    <div>
      <NuxtLink to="/">
        <Logo />
      </NuxtLink>
    </div>
    <div class="flex items-center">
      <div
        class="
          w-8
          h-8
          flex
          items-center
          justify-center
          mr-4
          rounded-full
          shadow-md
        "
      >
        <i :class="`${rotate} sidebarIcon text-darkPrimary el-icon-back cursor-pointer`" @click="toggleSidebar"></i>
      </div>
      <div class="hidden md:block">
        <el-input
          placeholder="Search for anything here"
          v-model="input3"
          class="input-with-select"
          suffix-icon="el-icon-search"
        >
          <el-select v-model="select" slot="prepend" placeholder="All">
            <el-option label="Restaurant" value="1"></el-option>
            <el-option label="Order No." value="2"></el-option>
            <el-option label="Tel" value="3"></el-option>
          </el-select>
        </el-input>
      </div>
    </div>

    <div>
      <div class="flex items-center">
        <div class="hidden md:block relative p-2 rounded-lg bg-primaryLight">
          <Notify />
          <span
            class="
              h-4
              w-4
              flex
              justify-center
              items-center
              rounded-full
              bg-red-500
              absolute
              top-0
              right-0
              text-white text-center
            "
          >
            <span class="text-white text-sm">2</span>
          </span>
        </div>
        <img class="hidden md:block ml-5 rounded-full" src="/user-1.png" alt="" />
        <el-dropdown class="ml-5">
          <span class="el-dropdown-link">
            Solomon<i class="el-icon-arrow-down el-icon--right"></i>
          </span>
          <el-dropdown-menu slot="dropdown">
            <el-dropdown-item>Profile</el-dropdown-item>
            <el-dropdown-item>Notification</el-dropdown-item>
            <el-dropdown-item>Settings</el-dropdown-item>
            <el-dropdown-item divided>Logout</el-dropdown-item>
          </el-dropdown-menu>
        </el-dropdown>
      </div>
    </div>
  </div>
</template>

<script>
import Logo from "@/assets/vectors/logo.vue";
import Notify from "@/assets/vectors/notify-icon.vue";
export default {
  components: {
    Logo,
    Notify,
  },
  data() {
    return {
      input1: "",
      rotate: false,
      input2: "",
      input3: "",
      select: "",
    };
  },
  methods: {
    toggleSidebar() {
      this.rotate = !this.rotate;
      this.$emit('isToggleSidebar');
    }
  }
};
</script>

<style>
#header .el-select {
  width: 94px;
}

.sidebarIcon.true {
  transition: all 0.45s;
  transform: rotate(180deg);
}

.sidebarIcon.false {
  transition: all 0.45s;
  transform: rotate(0deg);
}

#header .el-input-group {
  height: 58px;
  width: 890px;
  background: #f1f1f1;
}

#header .el-input__inner {
  height: 58px;
  background: #f1f1f1;
}
</style>