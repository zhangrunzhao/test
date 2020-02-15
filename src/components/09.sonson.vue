<template>
    <div>
        <h3 :style="{color: color}">孙子</h3>
        <hr>
    </div>
</template>

<script>
import {inject} from '@vue/composition-api'
export default {
    setup() {
        const color = inject('themeColor');
        return {
            color
        };
    }
}
</script>