<template>
  <vue-horizontal scroll>
    <component-example class="component" v-for="i in [1,2,3,4,5,6,7,8]" :key="i">
      <h3>Scroll bar {{i}}</h3>
    </component-example>
  </vue-horizontal>
</template>

<style scoped>
.component {
  margin-bottom: 24px;
}
</style>
