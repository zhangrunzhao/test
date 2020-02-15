<template>
    <div>
        <input type="text" v-model="kw">
    </div>
</template>

<script>
import {ref,watch,onBeforeMount,onMounted} from "@vue/composition-api"
export default {
    setup() {
        const kw = ref("");
        const asyncPrint = val => {
            return setTimeout(()=>{
                console.log(val);
            },500);
        };
        watch(kw, (newVal,oldVal,clean)=> {
            const timerId = asyncPrint(newVal);
            clean(()=>clearTimeout(timerId)) //清除之前没问完成的异步任务
        },{lazy:true});


        onBeforeMount(()=>{
            console.log("onBeforeMount");
        })

        onMounted(()=>{
            console.log("onMounted");
        })


        return {
            kw
        };
    },
    beforeMount() {
        console.log("onBeforeMount");
    },
    mounted() {
        console.log("onMounted");
    }
}
</script>