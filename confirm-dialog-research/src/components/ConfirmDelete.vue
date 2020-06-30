<template>
  <div>
    <b-modal v-model="showModal" :title="title" @ok="handleOk">
    <p class="my-4">{{ msg }}</p>
  </b-modal>
  </div>
</template>
<script>
export default {
  props: {
    title : {
      type : String
    },
    msg : {
      type : String
    },
    handleOk : {
      type : Function
    },
    modalShow : {
      type : Boolean
    }
  },
  computed : {
    showModal : {
      get : function(){
        return this.modalShow
      },
      set : function(value){
        return this.$emit('update:modalShow', value)
      }
    }
  },
};
</script>
