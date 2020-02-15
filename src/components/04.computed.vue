<template>
    <div>
        <p>count值为 {{refCount}}</p>
        <p>计算属性的值 {{computedCount}}</p>

        <button @click= "refCount+=1">+1</button>
    </div>
</template>
<script>
import {ref, computed} from '@vue/composition-api'
export default {
    setup() {
        const refCount = ref(0);
        const computedCount =  computed( ()=> refCount.value +1 );
        return {
            refCount,
            computedCount
        };
    }

}
</script>