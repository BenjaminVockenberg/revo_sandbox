<script setup>
import { ref } from 'vue';
import { VGrid, VGridVueEditor, VGridVueTemplate } from '@revolist/vue3-datagrid';

// TestEditors
import GenericCodeEditor from './components/GenericCodeEditor.vue';
import AnEditor from './components/AnEditor.vue';

const gridEditors = {
    codeEditor: VGridVueEditor(GenericCodeEditor),
    editor: VGridVueEditor(AnEditor),
}

const columns = [
    { prop: 'name', name: 'first', editor: 'codeEditor', size: 150, cellTemplate: VGridVueTemplate(GenericCodeEditor) },
    { prop: 'details', name: 'second', editor: 'editor', size: 200, cellTemplate: VGridVueTemplate(AnEditor)}
];

const rows = ref([
    { name: 'Samson', details: 'Gehen euch nix an!' }
]);
</script>

<template>
    <div>
        <v-grid :source="rows" :columns="columns" :editor="gridEditors" style="height:150px" :routerLink="false" />
    </div>
</template>

