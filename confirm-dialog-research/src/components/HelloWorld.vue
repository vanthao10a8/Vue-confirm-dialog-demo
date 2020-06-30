<template>
  <div>
    <ConfirmDeleteModal
      :modalShow.sync="modalShow"
      :title="title"
      :msg="deleteMsg"
      :handleOk="handleSubmit"
    ></ConfirmDeleteModal>
    <!-- person details -->
    <b-button @click="confirmDelete(true)">Launch demo modal</b-button>
  </div>
</template>

<script>
import ConfirmDeleteModal from "@/components/ConfirmDelete";
export default {
  components: {
    ConfirmDeleteModal,
  },
  data() {
    return {
      modalShow: false,
      deleteMsg: "",
      title: "",
    };
  },
  methods: {
    confirmDelete(val) {
      this.modalShow = val;
      this.title = "Delete Code?";
      this.deleteMsg = "You are deleting a code";
    },
    handleSubmit() {
      this.modalShow = false;
      alert("Submit oke");
    },
  },
};
</script>
