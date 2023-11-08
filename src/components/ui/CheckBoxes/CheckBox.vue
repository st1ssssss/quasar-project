<script setup lang="ts">
    import {watch, ref } from 'vue';
    interface CheckBoxProps{
        label: string,
        disable?: boolean
    }

    const props = withDefaults(defineProps<CheckBoxProps>(), {
        label: 'Вариант 1'
    })

    let isHovered = ref(false)
    let uncheckedIcon = 'svguse:imgs.svg#defaultCheckBox'

    watch(isHovered, ()=>{
        if (isHovered.value === true && !props.disable){
            uncheckedIcon='svguse:imgs.svg#hoverCheckBox'
        }else if (isHovered.value === false){
            uncheckedIcon='svguse:imgs.svg#defaultCheckBox'
        }
    })
</script>
<template>
    <q-checkbox 
      class="checkbox"
      v-model="isHovered"
      :label="label"
      :val="label"
      :disable="disable"
      checked-icon="svguse:imgs.svg#activeCheckBox"
      :unchecked-icon="uncheckedIcon"
      indeterminate-icon="svguse:imgs.svg#defaultCheckBox"
      @mouseover="isHovered = true"
      @mouseleave="isHovered = false"
    >

    </q-checkbox>
</template>
<style scoped lang="sass">

    .checkbox
        margin-top: 12px
        font-family: 'Inter'
        font-style: normal
        font-weight: 400
        font-size: 16px
        line-height: 19px
        color: #23211F

</style>