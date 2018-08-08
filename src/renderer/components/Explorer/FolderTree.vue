<template>
  <el-tree :props="props1" :load="loadNode1" lazy>
  </el-tree>
</template>

<script>
export default {
  name: 'folder-tree',
  data() {
    return {
      props1: {
        label: 'name',
        children: 'zones',
        isLeaf: 'leaf'
      },
    };
  },
  methods: {
    loadNode1(node, resolve) {
      console.log(node)
      console.log(resolve)
      if (node.level === 0) {
        return resolve([{ name: 'region' }]);
      }
      if (node.level > 1) return resolve([{ name: 'hoge' }]);

      setTimeout(() => {
        const data = [{
          name: 'leaf',
          leaf: true
        }, {
          name: 'zone'
        }];

        resolve(data);
      }, 500);
    }
  }
};
</script>

<style scoped>
</style>
