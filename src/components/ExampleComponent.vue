<template>
  <div class="container">
    <div>
      <ButtonToGo/>
      <ButtonToGo :disable="true" />
      <ButtonToGo pass/>
      <ButtonToGo pass :disable="true" />
    </div>
    <div>
      <ButtonSignUp/>
      <ButtonSignUp :disable="true" />
    </div>
    <div>
      <ButtonCQ/>
      <ButtonCQ :disable="true" />

    </div>
    <div class="sliders">
      <div class="group">
        <Slider left/> <Slider style="margin-left: 10px;"/> 
      </div>
      <Slider style="margin-top: 5px;" :disable="true" />
    </div>
    <div>
      <RadioButton v-model="radioM" text="Вариант 1"/>
      <RadioButton v-model="radioM" text="Вариант 2" :disable="true" />
      <RadioButton v-model="radioM" text="dfhbr ghbdntn"/>
      this is {{radioM}}
    </div>
    <div>
      <CheckBox v-model="checkM" label="v1"/>
      <CheckBox v-model="checkM" label="v2" :disable="true"/>
      <CheckBox v-model="checkM" label="v3"/>
      this is your choiсe {{ checkM }}
    </div>
  <div>
    <SelectCourse />
  </div>
  </div>
</template>

<script setup lang="ts">
import ButtonToGo from './ui/Buttons/ButtonToGo.vue';
import ButtonSignUp from './ui/Buttons/ButtonSignUp.vue'
import ButtonCQ from './ui/Buttons/ButtonCQ.vue'
import Slider from './ui/Buttons/Slider.vue';
import RadioButton from './ui/RadioButtons/RadioButton.vue'
import CheckBox from './ui/CheckBoxes/CheckBox.vue'
import SelectCourse from './ui/FilterCourse/SelectCourse.vue';
import { ref } from 'vue';

let radioM = ref('')
let checkM = ref ([])


</script>
<style lang="sass" scoped>
  *
    margin: 0
    padding: 0



  .Buttons
    display: flex
    flex-wrap: wrap

  .sliders
    display: flex
    flex-direction: column
    padding-left: 20px
    padding-top: 15px 

  .group
    display: flex

  
    
</style>
