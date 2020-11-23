<template>
    <h2>{{ state.count }}, doubled = {{ state.doubled }}</h2>
    <button @click="updateCount(true)">Increase</button>
    <button @click="updateCount(false)">Decrease</button>
</template>

<script>
// REF
// import { ref } from "vue";

// export default {
//     setup() {
//         const count = ref(0)

//         function updateCount(increase) {
//             if (increase)
//                 count.value++
//             else
//                 count.value--
//         }

//         return {
//             count,
//             updateCount
//         }
//     }
// }

// REACTIVE
import { reactive, computed } from "vue";

export default {
    setup() {
        const state = reactive({
            count: 0,
            doubled: computed(() => state.count * 2)
        })

        function updateCount(increase) {
            if (increase)
                state.count++
            else
                state.count--
        }

        return {
            state,
            updateCount
        }
    }
}
</script>

<style>

</style>