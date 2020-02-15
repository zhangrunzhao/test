<template>
    <div>
        <p>count值为 {{count}}</p>
        <button @click="count+=1">+1</button>
    </div>
</template>


<script>
import {reactive} from '@vue/composition-api'
export default {
    setup() { // props 代表外界传入的属性
        // window.console.log("setup");
        // window.console.log(props.p1);
        // window.console.log(ctx); 
        const state = reactive({count:0});
        console.log(state);
        state.count+=1; // 反手加个1
        console.log(state);
        return state
    },
    props: {
        p1: String // 声明

    }
}
</script>