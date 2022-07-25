<template>
  <button v-on:click="iAmClicked">You clicked me {{ count }} times.</button>
</template>


<script setup>
    import { defineProps, ref } from 'vue';

    const props = defineProps({
        rowIndex: { type: Number },
        model: { type: Object },
        close: { type: Function },
        save: { type: Function }
    })

    const count = ref(0);

    const iAmClicked = (e) => {
        return count.value++;
    }
</script>