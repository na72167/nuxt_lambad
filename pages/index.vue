<template>
    <div>
        <div> {{ message }} </div>
        <button @click="click">ボタン</button>
    </div>
</template>

<script lang="ts">
import Vue from 'vue'
import axios from 'axios'
export default Vue.extend({
    data(): {
      message: unknown
    } {
      return {
        message: ''
      }
    },
    methods: {
        async click():Promise<void> {
        const response = await axios.get('https://cldu07velj.execute-api.ap-northeast-1.amazonaws.com/prod/item')
        this.message = response.data
        }
    }
})
</script>
