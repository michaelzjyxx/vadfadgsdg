<template>
  <div class="hello">
  <h1>{{msg}}</h1>
    <input v-model="newCheck" @keyup.enter="addCheck">
    <ul>
      <li  v-for="item in items" :class="{finished:item.isFinished}" @click="check(item)">
      {{item.label}}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'hello',
  data () {
    return {
      msg: '我的清单',
      items:[
        {label:1,
          isFinished:false
        },
        {label:2,
          isFinished:false
          
        }
      ]
    }
  },
  methods:{
    check:function(item){
        item.isFinished=!item.isFinished;
      },
      addCheck:function(){
        this.items.push({
          label:this.newCheck,
          isFinished:false
        }),
        this.newCheck=""
      }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.finished{
  text-decoration: underline;
}
h1 {
  font-weight: normal;
}
</style>
