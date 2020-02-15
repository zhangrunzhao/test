<template>
    <div>
        <h2>子组件</h2>
        <p>{{str1}}</p>

        <hr>
        <com-sonson/>
    </div>
</template>

<script>
import {ref} from '@vue/composition-api'
import ComSonSon from './09.sonson';
export default {
    components: {
        'com-sonson': ComSonSon
    },
    setup() {
        const str1 = ref('this is 子组件')

        const setStr = ()=> {
            str1.value = '被赋值啦~~~'
        }

        return {
            str1,
            setStr
        }
    }
}
</script>
