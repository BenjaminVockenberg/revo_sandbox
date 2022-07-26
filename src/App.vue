<script setup>
import { ref } from 'vue';
import { VGrid, VGridVueEditor, VGridVueTemplate } from '@revolist/vue3-datagrid';

// TestEditors
import AnEditor from './components/AnEditor.vue';

const gridEditors = {
    editor: VGridVueEditor(AnEditor)
};

const columns = [
    { prop: 'name', name: 'first', editor: 'codeEditor', size: 150 },
    { prop: 'details', name: 'second', editor: 'editor', size: 200, cellTemplate: VGridVueTemplate(AnEditor) }
];

const rows = ref([
    { name: 'Samson', details: 'Gehen euch nix an!', story: true },
    { name: 'Detlef', details: 'Könnten detaillierter sein', story: false },
    { name: 'Rambo', details: 'Sven isr nicht da', story: false }
]);

const beforeFocus = (e) => {
    console.log(e);
    e.preventDefault();
};
</script>

<template>
    <div>
        <v-grid :source="rows" :columns="columns" :editor="gridEditors" style="height:150px" :routerLink="false" @beforeCellFocus="beforeFocus" />
    </div>
</template>

