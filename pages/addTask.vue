<template>
  <div>
    <div>
      <div>タスクの追加</div>
      <form @submit.prevent="addTask">
        <input type="text" placeholder="IDの記入" v-model="id">
        <input type="text" placeholder="タスクの追加" v-model="text">
        <button
          type="submit"
        >
        タスクの追加
        </button>
      </form>
    </div>
  </div>
</template>

次にやる事
タスク追加分のメソッド動作の確認
変更

<script lang="ts">
import { Component, Vue } from "nuxt-property-decorator";
import axios from 'axios'

@Component
export default class addTask extends Vue {

  public id: string | null = null;
  public text: string | null = null;

  public async addTask() {

    if(this.text !== null){
      try {
        console.log("タスク追加処理に入ります");
        const list = {
          name: this.text,
        }
        const registUser = await axios.post('',list);
      } catch (e) {
        console.log("登録処理中に例外エラーが発生しました。");
      }
    }

  }
}
</script>
