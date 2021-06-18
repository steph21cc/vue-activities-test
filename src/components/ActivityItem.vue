<template>
  <div>
    <ActivityItemUpdate v-if="isUpdateActive"
                        :activity="activity"
                        :categories="categories" 
                        @toogleUpdate="changeUpdateState" />
    <ActivityItemDetail v-else
                        :activity="activity" 
                        :categories="categories"
                        @toogleUpdate="changeUpdateState" />
  </div>
</template>

<script>

  import ActivityItemDetail from './ActivityItemDetail'
  import ActivityItemUpdate from './ActivityItemUpdate'

  export default {
    components: {
      ActivityItemDetail, ActivityItemUpdate
    },
    props: {
      activity:{
        type: Object,
        required: true
      },
      categories: {
        type: Object,
        required: true
      }
    },
    data() {
      return {
        isUpdateActive: false
      }
    },
    methods: {
      changeUpdateState (isUpdate) {
        this.isUpdateActive = isUpdate
      }
    }
  }
</script>

<style scoped>
  
</style>
