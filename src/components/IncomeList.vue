<template>
  <div class="income-list">
      <IncomeItem v-for="data in state.sortedIncome" :key="data.id" :income="data" @remove-item="removeItem" />
  </div>
</template>

<script>
import IncomeItem from './IncomeItem'

export default {
    props: {
        state: Object
    },
    setup(props,{emit}){
        function removeItem(id) {
      emit( 'remove-item', id );
    }
    return {
      IncomeItem,
      removeItem
    }
  }
    }


</script>


<style scoped>
  .income-list {
    margin-top: 30px;
    padding: 15px;
  }
</style>
