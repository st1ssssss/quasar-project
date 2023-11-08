<script setup lang="ts">
import { ref, watch } from 'vue';

    interface RadioProps{
        text: string,
        disable?: boolean,
    }
    const props = withDefaults(defineProps<RadioProps>(), {
        text: 'Вариант',
        disable: false
    })

    let isHovered = ref(false)
    let unchecked_icon = ref('')

    watch(isHovered, ()=>{
        if(isHovered.value === true && !props.disable){
            unchecked_icon.value = 'svguse:imgs.svg#uncheckedRadio'
        } else if (isHovered.value === false){
            unchecked_icon.value = 'svguse:imgs.svg#defaultRadio'   
        }
    })
    unchecked_icon.value = 'svguse:imgs.svg#defaultRadio'   


</script>
<template>
    <q-radio 
        :label="text"
        keep-color
        :val="text"
        :disable="disable"
        checked-icon="svguse:imgs.svg#checkedRadio"
        :unchecked-icon="unchecked_icon"
        class="radio-button"
        @mouseover="isHovered = true"
        @mouseleave="isHovered = false"
    >
    </q-radio> 
</template>
<style scoped lang="sass">
    .radio-button
        margin-top: 15px
        font-family: Inter
        font-size: 16px
        font-weight: 400
        line-height: 19px
        text-align: left

</style>
