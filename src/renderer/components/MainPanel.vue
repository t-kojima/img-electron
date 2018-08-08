<template>
  <multipane class="vertical-panes" layout="vertical">
    <div class="pane" :style="{ width: '320px', minWidth: '215px' }">
      <explorer />
    </div>
    <multipane-resizer> </multipane-resizer>
    <div class="pane">
      <landing-page />
    </div>
  </multipane>
</template>

<script>
import Explorer from './Explorer'
import LandingPage from './LandingPage'
import { Multipane, MultipaneResizer } from 'vue-multipane';

export default {
  name: 'main-panel',
  components: {
    Explorer, LandingPage, Multipane, MultipaneResizer
  },
  methods: {
  }
}
</script>

<style scoped>
.vertical-panes {
  width: 100%;
  height: 100vh;
  border: 1px solid #ccc;
}
.vertical-panes > .pane {
  text-align: left;
  padding: 3px;
  overflow: hidden;
  /* background-color: #545c64;
  color: #fff; */
}
.vertical-panes > .pane ~ .pane {
  border-left: 2px solid #ccc;
}
</style>