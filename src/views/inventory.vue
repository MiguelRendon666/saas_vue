<template>
    <h2>Template de Formulario</h2>
    <FormGroupComponent title="Titulo del grupo">
        <TextInputComponent :propertyName="'TextoNormal'"/>
    </FormGroupComponent>
</template>

<script>
import FormGroupComponent from '@/components/Form/FormGroupComponent.vue';
import TextInputComponent from '@/components/Form/TextInputComponent.vue';

export default {
    name: 'InventoryView',
    components: {
        FormGroupComponent,
        TextInputComponent
    },
}
</script>