<script setup lang="ts">
    import { ref } from 'vue';
    interface SliderProps{
        left?: boolean,
        disable?: boolean,
    }
    const props = withDefaults(defineProps<SliderProps>(),{
        left: false,
        disable: false
    })

    const isHovered = ref(false)
    const isPressed = ref(false)
</script>
<template>
    <button class="slider" 
    :class="{
        left: left,
        disabled: disable,
        hovered: isHovered,
        pressed: isPressed,
    }"

    @mouseover="isHovered = true"
    @mouseleave="isHovered = false"
    @mousedown="isPressed = true"
    @mouseup="isPressed = false">
    <q-icon size="10px" name="svguse:imgs.svg#slider"></q-icon></button>
</template>
<style scoped lang="sass">
    .slider
        display: flex
        align-items: center
        justify-content: center
        width: 32px
        height: 32px
        border-radius: 8px
        background-color: var(--q-current)
        border: 0
    .left
        transform: rotate(180deg)
    .hovered
        background: var(--q-current-hover)
    .pressed
        background-color: var(--q-current-pressed)
    .disabled
        background-color: var(--q-current-disabled)
</style>