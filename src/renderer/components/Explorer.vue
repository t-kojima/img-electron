<template>
  <div>
    <h5>Custom colors</h5>
    <el-menu :default-active="activeIndex" mode="horizontal" @select="handleSelect">
      <el-menu-item index="1">
        <i class="el-icon-menu"></i>
      </el-menu-item>
      <el-menu-item index="2">
        <i class="el-icon-search"></i>
      </el-menu-item>
      <el-menu-item index="3">
        <i class="el-icon-setting"></i>
      </el-menu-item>
    </el-menu>
    <folder-tree v-if="activeIndex==1" />
  </div>
</template>

<script>
import FolderTree from './Explorer/FolderTree'

export default {
  name: 'explorer',
  data() {
    return {
      activeIndex: '1',
    };
  },
  methods: {
    handleSelect(key, keyPath) {
      this.activeIndex = key
    }
  },
  components: { FolderTree }
}
</script>

<style scoped>
</style>
