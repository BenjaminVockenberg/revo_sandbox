<template>
  <input type="text" v-model="value" @input="DoStuff()">
</template>


<script setup>
    import { defineProps, ref, watch } from 'vue';

    const props = defineProps({
        rowIndex: { type: Number },
        model: { type: Object },
        close: { type: Function },
        save: { type: Function },
        data: { type: Object },
        prop: { type: String },
        column: { type: Object }
    });

    const value = ref(props.data[props.rowIndex][props.prop]);

    const DoStuff = () => {
        console.log("Toasties");
    }
</script>