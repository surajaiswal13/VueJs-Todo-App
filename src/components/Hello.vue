<template>
    <div>
        <!-- <h2>Hello Commponent 2 [ Hello.Vue ]</h2> -->
        <h2>{{ Hello_msg }}</h2>

    </div>
</template>

<script>
// import { defineComponent } from '@vue/composition-api'
// export default defineComponent({
export default {
    name:'Home',
    props: {
    Hello_msg: String


    }
}
//     export default {
//   name: 'HelloWorld',
//   props: {
//     msg: String
//   }
// }
</script>
