<template>
  <v-container fill-height>
    <v-row>
      <v-col>
        <CommunityCard
          v-for="(cardType,index) in cardList"
          :key="index"
          :community-type="cardType"
        />
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
import CommunityCard from '@/components/community/CommunityCard.vue';

export default {
  name: 'BaseCommunityDefault',
  components: {
    CommunityCard,
  },
  data: () => ({
    cardList: ['popular information', 'popular questions', 'information', 'questions'],
  }),
  created() {
    for (let i = 0; i < this.cardList.length; i += 1) {
      const j = Math.floor(Math.random() * (i + 1));
      const x = this.cardList[i];
      this.cardList[i] = this.cardList[j];
      this.cardList[j] = x;
    }
  },

};
</script>

<style scoped>

</style>
