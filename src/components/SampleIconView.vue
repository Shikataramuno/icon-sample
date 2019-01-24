<template>
  <div class="sample-icon-field">
    <img src="../assets/SampleIcon.png" class="icon" width='30px' height='30px' @click="iconClicked"/>
    <div class="message">{{message}}</div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class SampleIconView extends Vue {
  name: string = 'SampleIconView';
  message: string = ' ↑ クリック^2 ！';
  clickCount: number = 0;
  iconClicked(): void {
    alert('アイコンがクリックされました！');
    this.clickCount++;
    this.message = ' アイコンが ' +  this.clickCount + '回 クリックされました！';
  }
  created(): void {
    console.log('SampleIconView.created');
  }
}
</script>

<style scoped>
.sample-icon-field {
  padding: 5px;
  width: 100%;
}
.message {
  line-height: 30px;
}
</style>
