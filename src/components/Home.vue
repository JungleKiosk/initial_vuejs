<script>

import { ref } from 'vue'

const count = ref(0)

import data from '../data/data.js'

export default {
  name: 'Home',
  data() {
   return {
      cards: data,
      searchCard: '',
    };
  },
  computed:{
    filteredCard(){
      if (!this.searchCard){
        return this.cards;
      }
      const query = this.searchCard.toLowerCase();

      return this.cards.filter(card =>
        card.title.toLowerCase().includes(query) ||
        card.desc.toLowerCase().includes(query) ||
        card.icon.toLowerCase().includes(query)
      )
    }
  }
}

const cards = ref(data);


</script>

<template>
  <div class="container mt-5">
    <div class="row justify-content-center">
      <div class="col-3">
        <input type="text" class="form-control" placeholder="Search card..." v-model="searchCard">
      </div>
      <div class="col-3 text-center" v-for="card in filteredCard">
        <div class="card">
          <div class="card-body">
            <div class="card-title">
              {{ card.title }}
            </div>
            <div class="card-text">
              {{ card.desc }}
            </div>
            <div class="card-footer">
              {{ card.icon }}
            </div>
          </div>


          <button class="btn btn-danger" @click="count++">{{ count }}</button>

        </div>
      </div>
    </div>
  </div>


</template>

<style scoped></style>
