<script setup lang="ts">
import { ref } from 'vue';
let selectM = ref({label: 'Все курсы', value: 'course'})

let selectOptions = [
  {label: 'Все курсы', value: 'course'},
  {label: 'Активные курсы', value: 'active'},
  {label: 'Законченные курсы', value: 'ended'},

]
</script>
<template>
    <q-select
        :options="selectOptions"
        v-model="selectM"
        borderless
        no-wrap
        dense
        hide-dropdown-icon
        color="black"
        :class="{
            allSelect: selectM.value === selectOptions[0].value,
            activeSelect: selectM.value === selectOptions[1].value,
            endedSelect: selectM.value === selectOptions[2].value,

        }"
        popup-content-style="
          width: 15%;
          text-align: left;
          background: #FDFDFD;
          border: 1px solid #EAEDF1;
          border-radius: 16px;
          font-family: Inter;
          font-style: normal;
          font-weight: normal;
          font-size: 16px;
          "
    >
    <template v-slot:append>
        <q-icon 
        name="svguse:imgs.svg#selectArrow"
        style="width: 10px; height: 8px; margin-right: 14px; margin-top: 6px"/>
    </template>
    <template v-slot:selected>
        <p class="selected-text">{{ selectM.label }}</p>
    </template>
    </q-select>
</template>
<style scoped lang="sass">
.allSelect
  height: 48px
  width: 139px
  border: 1px solid #DCDFE2
  border-radius: 12px
.activeSelect
  height: 48px
  width: 184px
  border: 1px solid #DCDFE2
  border-radius: 12px
.endedSelect
  height: 48px
  width: 217px
  border: 1px solid #DCDFE2
  border-radius: 12px
.selected-text
  backround-color:#EAEDF1
  margin-top: 10px
  margin-left: 15px
  font-family: Inter
  font-style: regular
  font-size: 16px
  text-align: left
</style>