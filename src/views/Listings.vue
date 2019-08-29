<template>
  <div class="registration">
    <h1>New Project Listings</h1>

    <div class="listingHolder">
      <div v-for="item in listings">
        <div class="listing">
          <div class="row">
            {{ item.title }}
          </div>
          <div class="row">
            {{ item.city }}
          </div>
          <div class="row">
            <span class="detailBox">
              {{ item.roi }}%
            </span>
            <span class="detailBox">
              {{ item.months }} Monate
            </span>
            <span class="detailBox">
              {{ item.financeGoal }} Euro
            </span>
          </div>
          <div class="row">
            Finanziert {{ item.financeCurrent}} Euro
          </div>
          <div class="row">
            {{ item.financedPercentage}}%
          </div>
          <div class="row">
            Anlagklasse {{ item.ratingClass}}
          </div>
          <div class="row">
            <input type="button" v-if="item.status === 'active'" value="Zum Start Informien">
            <input type="button" v-if="item.status === 'closed'" value="Details">
          </div>  
        </div>
      </div>
    </div>
  </div>  
</template>

<script>

export default {
  name: 'Listings',
  data() {
    return {
      listings: [
        {
          title: 'Modern Living Schwabing',
          city: 'Munchen',
          roi: 5.2,
          months: '24',
          financeGoal: 680000,
          financeCurrent: 0,
          financedPercentage: 0,
          ratingClass: 'A',
          status: 'active',
        },
        {
          title: 'Apartments Bona Nova Servera',
          city: 'Palma de Mallorca',
          roi: 5.8,
          months: '23',
          financeGoal: 2130000,
          financeCurrent: 2130000,
          financedPercentage: 100,
          ratingClass: 'A',
          status: 'closed'
        },
      ]
    }
  },  
  mount: {
    returnListing() {
      return 
    }
  },
  methods: {
  },
};
</script>

<style scoped>
.listingHolder {
  display: flex;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  margin: 20px;
}
.listing {
  width: 300px;
  margin: 30px 15px;
}
.row {
  margin: 10px;
  text-align: left;
  @media screen and (max-width: 500px) {
    margin: 10px 5px;
  }
}
.detailBox {
  background-color: rgb(235, 237, 236);
  min-height: 25px;
  padding: 5px;
  margin: 2px;
}
</style>
