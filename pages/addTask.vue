<template>
<div>
  <div>
    <div>タスクの追加</div>

  </div>
</div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios'
export default Vue.extend({
data() :{ taskList: Array<{id:any, name:any}> } {
    return {
    taskList: []
    }
},
async mounted() {
    // 画面描画時にタスクの全件取得を行う
    this.taskList = []
    const response = await axios.get('https://cldu07velj.execute-api.ap-northeast-1.amazonaws.com/prod/item')
    this.taskList = response.data.Items
},

})
</script>
