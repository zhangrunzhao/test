<template>
    <div></div>
</template>

<script>
import {watch,reactive} from "@vue/composition-api"
export default {
    setup(){
        // const refCount = ref(0);

        // // watch默认情况下 组件在第一次创建的时候就执行了一次 如果不想它执行 就得传一个参数 {lazy:false}
        // watch(()=>console.log(refCount.value));

        // setTimeout(()=>{
        //     refCount.value += 1;
        // },1500);

        // const state = reactive({
        //     count: 0
        // })

        // watch(()=>state.count,
        //     (newVal,oldVal)=>{
        //         console.log(newVal,oldVal)
        //     },
        //     {lazy:true}
        // );
        // setTimeout(()=>{
        //     state.count += 1;
        // },1500);

         const state = reactive({
            count: 0,
            name: 'zs'
        })

        watch([()=>state.count,()=>state.name],
            ([newCount,newName],[oldCount,oldName])=>{
                console.log(newCount,newName)
                console.log(oldCount,oldName)
            },
            {lazy:true}
        );
        setTimeout(()=>{
            state.count += 1;
        },1500);
        setTimeout(()=>{
            state.name += "帅气";
        },3000);
    }
}
</script>