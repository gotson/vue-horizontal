<template>
  <div>
    <vue-horizontal class="20-items">
      <section v-for="item in items" :key="item.i">
        <div class="header">
          <h6>{{ item.i }}</h6>
          <h3>{{ item.title }}</h3>
        </div>
        <p>{{ item.content }}</p>
      </section>
    </vue-horizontal>

    <vue-horizontal class="2-items">
      <section v-for="item in items.slice(0, 2)" :key="item.i">
        <div class="header">
          <h6>{{ item.i }}</h6>
          <h3>{{ item.title }}</h3>
        </div>
        <h6>COUNT: 2</h6>
        <p>{{ item.content }}</p>
      </section>
    </vue-horizontal>

    <vue-horizontal class="fixed-content">
      <section>
        <div class="header">
          <h6>0</h6>
          <h3>fixed content</h3>
        </div>
        <p>Created without v-for fixed width item 0</p>
      </section>
      <section>
        <div class="header">
          <h6>1</h6>
          <h3>fixed content</h3>
        </div>
        <p>Created without v-for fixed width item 11</p>
      </section>
      <section>
        <div class="header">
          <h6>2</h6>
          <h3>fixed content</h3>
        </div>
        <p>Created without v-for fixed width item 222</p>
      </section>
    </vue-horizontal>
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import VueHorizontal from '@/vue-horizontal.vue';
import {Lorem} from './utils'

export default Vue.extend({
  components: {
    VueHorizontal
  },
  data() {
    const lorem = Lorem("content-width")
    return {
      items: [...Array(20).keys()].map((i) => {
        return {
          i,
          title: lorem.generateWords(2),
          content: lorem.generateWords(6),
        };
      }),
    }
  },
});
</script>

<style scoped>
section {
  padding: 16px 24px;
  border-radius: 4px;
  background: #f5f5f5;
  margin-right: 24px;
}

.header {
  display: flex;
}

.header h6 {
  background: #0000db;
  font-size: 14px;
  color: white;
  width: 24px;
  height: 24px;
  text-align: center;
  line-height: 24px;
  border-radius: 12px;
  margin-right: 12px;
}
</style>
