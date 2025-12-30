<template>
<div class="TextInput">
    <label for=""></label>
    <input type="text" />
</div>
</template>

<script lang="ts">
export default {
    name: 'TextInputComponent',
    props: {
        propertyName: {
            type: String,
            required: true,
            default: '',
        },
    },
    emits: ['update:modelValue'],
    watch: {
        modelValue(newValue) {
            this.$emit('update:modelValue', newValue);
        }
    },
    data() {
        return {
            textInputId: 'text-input-' + this.propertyName,
        }
    },
}
</script>