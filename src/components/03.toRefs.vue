<template>
    <div>
        <p>count值为{{count}}</p>
        <button @click="add">+1</button>
    </div>
</template>
<script>
import {reactive, toRefs} from "@vue/composition-api";
export default {
    setup() {
        const state = reactive({count:0,name: 'zs'});

        // 定义自增+1的函数
        // 函数最好也写进setup中
        const add = () => {
            state.count+=1;
        }

        return {
            ...toRefs(state), // 这样会把state里面的每一个属性都转化为ref
            add
        };
    }
}
</script>