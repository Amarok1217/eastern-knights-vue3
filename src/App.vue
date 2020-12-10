<template>
  <div>
    <button
      v-for="(item,index) in list"
      :key="index"
      @click="chooseItem(index)"
    >{{index}}.{{item}}</button>
    <div>{{currentItem}}</div>
  </div>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
export default defineComponent({
  name: 'App',
  setup() {
    const text: string = 'aaa';
    const list = ref(['a', 'b', 'c']);
    const currentItem = ref('');
    const chooseItem = (index: number) => {
      console.log(index);
      currentItem.value = list.value[index];
    };

    return { list, currentItem, chooseItem };
  },
});
</script>

<style lang="scss">
// #app {
//   font-family: Avenir, Helvetica, Arial, sans-serif;
//   -webkit-font-smoothing: antialiased;
//   -moz-osx-font-smoothing: grayscale;
//   text-align: center;
//   color: #2c3e50;
// }

// #nav {
//   padding: 30px;

//   a {
//     font-weight: bold;
//     color: #2c3e50;

//     &.router-link-exact-active {
//       color: #42b983;
//     }
//   }
// }
</style>
