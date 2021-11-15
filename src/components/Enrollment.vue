<template>
    <button @click="onClick()" :style="{background: color}" class="btn btn-enroll">{{text}}</button>
</template>
<script>

export default{
  name: 'Enrollment',
  props:{
      text:String,
      color:String
  },
  methods:{
      onClick(){
          this.$emit('btn-click')
      },
  }
}
</script>
