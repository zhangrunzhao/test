<template>
    <div>
        <!-- <p>refCount的值为 {{refCount}}</p>
        <button @click="refCount+=1">+1</button> -->
    </div>
</template>
<script>
import {ref,reactive} from '@vue/composition-api';
export default {
    setup() {
        const c1 = ref(0);
        const state = reactive({
            c1
        })
        // 再次创建 ref, 命名为 c2
        const c2 = ref(9);
        state.c1 = c2;
        state.c1++;
        console.log(state.c1);// 输出10
        console.log(c2.value);// 输出10
        console.log(c1.value);// 输出0
    }
}
</script>