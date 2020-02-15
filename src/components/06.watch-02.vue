<template>
    <div>
        <p>count {{refCount}}</p>
        <button @click="stopWatch">停止监听</button>
    </div>
</template>

<script>
import { ref,watch } from '@vue/composition-api'
export default {
    setup() {
        const refCount = ref(0);

        const stop =  watch(()=>console.log(refCount.value));
        
        setTimeout(()=>{
            refCount.value += 1
        },3000)
        const stopWatch = () =>{
            stop() //停止监视
        };
        return {
            refCount,
            stopWatch
        }
    }
}
</script>
