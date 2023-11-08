<script setup lang="ts">
    import { ref } from 'vue';

    interface ButtonProps{
        disable?: boolean
        pass?: boolean
    }
    const props = defineProps<ButtonProps>()

    const isHovered = ref(false)
    const isPressed = ref(false)



</script>
<template>
    <button class="btn" 
    :class="{
        hovered: isHovered,
        pressed: isPressed,
        disabled: disable,
        passed: props.pass,
        hoveredPassed: isHovered && props.pass,
        pressedPassed: isPressed && props.pass,
        disabledPassed: disable && props.pass,
    }"
    
      @mouseover="isHovered = true"
      @mouseleave="isHovered = false"
      @mousedown="isPressed = true"
      @mouseup="isPressed = false">
        <q-icon size="20px" name="svguse:imgs.svg#arrow"/>
    </button>
</template>
<style scoped lang="sass">

    .btn
        height: 48px
        width: 48px
        margin-top: 20px
        margin-left: 20px
        border-radius: 16px
        border: 0
        background: var(--q-current)
    .hovered
        background: var(--q-current-hover) 
    .pressed
        background-color: var(--q-current-pressed)
    .disabled
        background-color: var(--q-current-disabled)
    .passed
        background: var(--q-passed)

    .hoveredPassed
        background: var(--q-passed-hover)
    .pressedPassed
        background-color: var(--q-passed-pressed)
    .disabledPassed
        background-color: var(--q-passed-disabled)

</style>