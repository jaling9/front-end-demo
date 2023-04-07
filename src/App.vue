<template>
  <div class="flex-div">
    <div class="card flex-layout">
      <div class="flex-Box">
        <h4>flex-direction</h4>
        <p>排列方向</p>
        <Dropdown
          v-model="direction"
          :options="value"
          optionLabel="name"
          placeholder="默认row"
          class="w-full md:w-14rem"
        />
      </div>

      <div class="flex-Box">
        <h4>justify-content</h4>
        <p>子元素在横轴上的对齐方式</p>
        <Dropdown
          v-model="content"
          :options="value2"
          optionLabel="name"
          placeholder="默认flex-start"
          class="w-full md:w-14rem"
        />
      </div>

      <div class="flex-Box">
        <h4>align-items</h4>
        <p>子元素在纵轴上的对齐方式</p>

        <Dropdown
          v-model="alignItems"
          :options="value3"
          optionLabel="name"
          placeholder="默认stretch"
          class="w-full md:w-14rem"
        />
      </div>

      <div class="flex-Box">
        <h4>flex-wrap</h4>
        <p>子元素换行:内容溢出的时候开启</p>

        <Dropdown
          v-model="flexWrap"
          :options="value4"
          optionLabel="name"
          placeholder="默认nowrap"
          class="w-full md:w-14rem"
        />
      </div>

      <div class="flex-Box">
        <h4>align-content</h4>
        <p>换行后子元素的对齐方式</p>
        <Dropdown
          v-model="alignContent"
          :options="value5"
          optionLabel="name"
          placeholder="默认stretch "
          class="w-full md:w-14rem"
        />
      </div>
    </div>

    <div class="card">
      <div
        class="flex flex-container"
        :style="{
          'flex-direction': direction.name,
          'justify-content': content.name,
          'align-items': alignItems.name,
          'flex-wrap': flexWrap.name,
          'align-content': alignContent.name,
        }"
      >
        <div class="card flex flex-item item1"></div>
        <div class="card flex flex-item"></div>
        <div class="card flex flex-item"></div>
        <div class="card flex flex-item"></div>
        <div class="card flex flex-item"></div>
        <div class="card flex flex-item"></div>
        <div class="card flex flex-item"></div>
        <div class="card flex flex-item"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
import { ref, reactive } from 'vue';

const value = ref([
  { name: 'row' },
  { name: 'row-reverse' },
  { name: 'column' },
  { name: 'column-reverse' },
]);
const value2 = ref([
  { name: 'flex-start' },
  { name: 'flex-end' },
  { name: 'center' },
  { name: 'space-between' },
  { name: 'space-around' },
]);
const value3 = ref([
  { name: 'stretch' },
  { name: 'flex-start' },
  { name: 'flex-end' },
  { name: 'center' },
  { name: 'baseline' },
]);
const value4 = ref([
  { name: 'nowrap' },
  { name: 'wrap' },
  { name: 'wrap-reverse' },
]);
const value5 = ref([
  { name: 'stretch' },
  { name: 'flex-start' },
  { name: 'flex-end' },
  { name: 'center' },
  { name: 'space-between' },
  { name: 'space-around' },
]);

const direction = ref('row'); // 这里要写空字符串
const content = ref('');
const alignItems = ref('');
const flexWrap = ref('wrap');
const alignContent = ref('');

console.log('direction', direction);
console.log('direction.name', direction.name);
</script>

<style>
.flex-container {
  display: -webkit-flex;
  display: flex;
  width: auto;
  height: 500px;
  overflow: auto;
}
.flex-item {
  background-image: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  width: 200px;
  height: 200px;
  margin: 10px;
  /* flex-shrink: 1;
  flex-grow: 1;
  flex-basis: 50%; */
}
.item1 {
  /* flex: 1; */
  /* align-self: center; */
  /* 设置单个元素的位置 */
}
.flex-div {
  display: flex;
  flex-direction: column;
}
.flex-layout {
  /* width: auto; */
  padding: 10px;
  display: flex;
  margin-top: 0px;
  margin-left: 0px;
  margin-right: 0px;
  margin-bottom: 12px;
  flex-direction: row;
  justify-content: flex-start;
  align-items: flex-start;
  flex-wrap: wrap;
  align-content: flex-start;
}
.flex-Box {
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
  margin: 4px;
  padding: 4px;
  width: 200px;
  height: 100px;
}
h4 {
  font-family: arial;
  padding: 0px;
  margin-top: 0px;
  margin: 0px;
  color: rgb(85, 93, 101);
  font-size: 1.2rem;
}
p {
  padding: 0px;
  margin-top: 0px;
  margin: 0px;
  color: rgb(146, 160, 173);
  font-size: 12px;
}
/* Dropdown:placeholder {
  color: rgb(216, 80, 26);
  font-size: 12px;
} */
</style>
