<template>
  <div>
    <STButton>我是默认</STButton>
    <STButton type="primary" size="large">我是主要</STButton>
    <STButton type="danger" size="small" @click="handle">我是危险</STButton>
    <STEditor v-model="content"></STEditor>
  </div>
</template>

<script>
import STButton from '@/components/STButton'
import STEditor from '@/components/STEditor'
export default {
 components: {
   STButton,
   STEditor
 },
 data(){
   return{
     content: "我是编辑器"
   }
 },
 methods: {
   handle(e){
     console.log(e)
   }
 }
}
</script>

<style>

</style>