<script setup>
const emit = defineEmits(['update:checked'])

const updateChecked = (event) => {
            emit('update:checked', event.target.checked)
        }

const props = defineProps({
    name: {
        type: String,
        default: ''
    },
    id: {
        type: String,
        default: ''
    },
    label: {
        type: String,
        default: ''
    },
    checked: {
        type: Boolean,
        default:false
    },
    type: {
        type: String,
        required:true
    },

})
</script>

<template>
<div class="check">
    <input
        class="check__input"
        :type="type"
        :name="name"
        :id="id"
        :checked="checked"
        @change ="updateChecked($event)"
    >
    <label class="check__label" :for="id">
        {{ label }}
    </label>
</div>
</template>

<style lang="scss" scoped>
.check {
    display: flex;
    align-items: center;
    justify-content: space-between;
    width: 100px;



    &__input {
        width: 20px;
        height: 20px;
        border-radius: 3px;


        &-color {
            border: none;
            outline: none;
            width:25px;
            height: 25px;

        }
    }

    &__label {
        font-size: 20px;
        color: var(--label);
    }
}

.check, .check__input , .check__label {
    cursor: pointer;
}


</style>
