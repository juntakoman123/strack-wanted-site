<template>
  <div class="strackOut container" id="strackOut">
    <div class="row">
      <div class="col-12 col-sm-6 col-md-4" v-for="(row, index) in codeBehind.Papers">
        <WantedPaper
          :uuid="row.uuid"
          :name="row.name"
          :prize_money="row.prize_money"
          :warning="row.warning"
          :image="row.image_base64"
          :done="row.done"
          :is_done="row.IsDone"
          @onTouchedBubbleEvent="codeBehind.SaveDone(row)" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
// import HelloWorld from '@/components/HelloWorld.vue'; // @ is an alias to /src
import WantedPaper from '@/components/wanted.paper.vue';
import StrackOutBehind from '@/app.codebehinds/strackout/strackout.behind.ts';
import TrWanted from '@/app.entities/tr.wanted.ts';

@Component({
  components: {
    // HelloWorld,
    WantedPaper,
  },
})
export default class StrackOut extends Vue {

  protected codeBehind = new StrackOutBehind();

  constructor() {
    super();
  }
}
</script>
