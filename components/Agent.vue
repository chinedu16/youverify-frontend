<template>
  <div class="" id="agents">
    <el-tabs v-model="activeName" @tab-click="handleClick">
      <el-tab-pane label="All " name="first">
        <div v-for="i in 4" :key="i">
          <SingleAgent />
        </div>
      </el-tab-pane>
      <el-tab-pane label="Online" name="second">
        <div v-for="i in 2" :key="i">
          <SingleAgent />
        </div>
      </el-tab-pane>
      <el-tab-pane label="Offline" name="third">
        <div v-for="i in 2" :key="i">
          <SingleAgent />
        </div>
      </el-tab-pane>
    </el-tabs>
  </div>
</template>

<script>
import SingleAgent from "./modules/SingleAgent.vue";
export default {
  components: {
    SingleAgent,
  },
  data() {
    return {
      activeName: "first",
    };
  },
  methods: {
    handleClick(tab, event) {
      console.log(tab, event);
    },
  },
};
</script>

<style>
#agents .el-tabs__nav-scroll {
  padding: 0px 20px;
}


#agents .el-tabs__item {
  padding: 0px 20px 0px 0px;
  color: #C4C4C4;
  outline: none;
}

#agents .el-tabs__item.is-active {
  color: #023a59;
}

#agents .el-tabs__active-bar {
  background-color: #023a59;
}
</style>