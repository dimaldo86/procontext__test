<script>
import { ref } from 'vue'
import BaseCheckbox from '@/components/ui/BaseCheckbox.vue'

const isChecked = ref(false)

const isOpen = ref(false)

let showCheck = () => {
    return isOpen.value = !isOpen.value
}
</script>

<template>
<div class="checkbox">
    <div class="checkbox__title" @click="showCheck">
        <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-chevron-right checkbox__arrow" viewBox="0 0 16 16" :class="{ open: isOpen }">
            <path fill-rule="evenodd" d="M4.646 1.646a.5.5 0 0 1 .708 0l6 6a.5.5 0 0 1 0 .708l-6 6a.5.5 0 0 1-.708-.708L10.293 8 4.646 2.354a.5.5 0 0 1 0-.708z" />
        </svg>
        <div>List 1</div>
    </div>

    <div class="checkbox__group" :="checkOpen" :class="{ open: isOpen }">
        <BaseCheckbox
            name="checkbox"
            id="checkbox_item1"
            type="checkbox"
            label="item 1"
            v-model:checked="isChecked"
        ></BaseCheckbox>
        <BaseCheckbox
            name="checkbox"
            id="checkbox_item2"
            type="checkbox"
            label="item 2"
            v-model:checked="isChecked"
        ></BaseCheckbox>
        <BaseCheckbox
            name="checkbox"
            id="checkbox_item3"
            type="checkbox"
            label="item 3"
            v-model:checked="isChecked"
        ></BaseCheckbox>
        <BaseCheckbox
            name="checkbox"
            id="checkbox_item4"
            type="checkbox"
            label="item 4"
            v-model:checked="isChecked"
        ></BaseCheckbox>
    </div>

</div>
</template>

<style lang="scss" scoped>
.checkbox {
    &__group {
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        justify-content: center;
        padding-left: 50px;
        width: 100%;
        opacity: 0;
        overflow: hidden;
        max-height: 0;
        transition: var(--transition);

        &.open {
            opacity: 1;
            overflow: visible;
            max-height: 150px;

        }
    }

    &__title {
        display: flex;
        align-items: center;
        width: 100%;
        cursor: pointer;
        height: 30px;
        transition: var(--transition);

        &:hover {
            box-shadow: 3px 6px 24px 17px rgba(138, 149, 157, 0.2);
        }

        div {
            position: relative;
            margin-left: 10px;
            top: 0;
            left: 30px;

            &::after {
                content: '';
                position: absolute;
                top: 50%;
                transform: translateY(-50%);
                left: -30px;
                width: 16px;
                height: 16px;
                border: 1px solid black;
                border-radius: 3px;

            }
        }
    }

    &__arrow {
        transition: var(--transition);

        &.open {
            transform: rotate(90deg);
        }
    }
}
</style>
