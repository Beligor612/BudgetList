<template>
  <div class="item">
    <span class="budget-comment">{{item.comment}}</span>
    <span class="budget-value">{{item.value}}</span>
    <el-button
    type="danger"
    size="mini"
    @click="deleteItem(item.id)">
      Delete
    </el-button>
  </div>
</template>

<script>
export default {
  name: "BudgetListItem",
  props: {
    item: {
      type: Object,
      default: ()=>{},
    }
  },
  data: ()=> ({

  }),
  methods: {
    deleteItem(id){
      const isConfirm = confirm("Delete budget item?")
      if(isConfirm){
        this.$emit('deleteItem', id)
      }
    }
  }
}
</script>



<style scoped>

.item{
    display: flex;
    align-items: center;
    padding: 10px 15px
  }
.budget-value{
    font-weight: bold;
    margin-left: auto;
    margin-right: 20px;
  }
</style>