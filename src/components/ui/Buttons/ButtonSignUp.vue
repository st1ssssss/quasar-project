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
    }"
    
      @mouseover="isHovered = true"
      @mouseleave="isHovered = false"
      @mousedown="isPressed = true"
      @mouseup="isPressed = false">
        Записаться
    </button>
</template>
<style scoped lang="sass">

    .btn
        font-family: Inter
        height: 48px
        padding: 10px 24px
        margin-top: 20px
        margin-left: 20px
        border-radius: 8px
        border: 0
        background: var(--q-current)
    .hovered
 
        background: var(--q-current-hover)
        
    .pressed

        background-color: var(--q-current-pressed)
    .disabled

        background-color: var(--q-current-disabled)


</style>