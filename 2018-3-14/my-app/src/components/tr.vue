<template>
    <tr>
        <td><input type="checkbox" v-model="pval.checked"></td>
        <td>{{pval.id}}</td>
        <td>{{pval.name}}</td>
        <td>{{pval.price}}</td>
        <td>
            <input 
                type="button" 
                value="删除"
                @click="remove"
            />
            <input 
                type="button" 
                value="上移"
                @click="up"
            >
            <input 
                type="button" 
                value="下移"
                @click="downFn"
            >
        </td>
    </tr>
</template>
<script>
export default {
  name:"Tr",
  props:['pval'],
  methods:{
      remove(){
        this.$emit('prm',this.pval.id);
      },
      up(){
          this.$emit('pup',this.pval.id);
      },
      downFn(){
        this.$emit('pdown',this.pval.id);
      }
  }
}
</script>

