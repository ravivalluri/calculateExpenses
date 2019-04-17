<template>
  <section id="home-section" class="col col-all">
    <article id="home-current" class="widget">
      <section class="content">
        <p></p>
        <p>Today's Budget</p>
        <p>{{moneyForToday}}💰</p>
        <button v-on:click="add">Spending Amount</button>
        <p></p>
      </section>
    </article>

    <article id="home-expenditures" class="widget">
      <section class="content">
        <p>
          <span>💰</span>
          <span>Details</span>
        </p>

        <p v-for="expenditure in expenses" :key="expenditure.datetime">
          <span>{{expenditure.summ}}💰</span>
          <span>{{expenditure.description}}</span>
        </p>
      </section>
    </article>

    <article id="home-other" class="widget">
      <section class="content">
        <span v-on:click="editBudget" class="edit">⚙</span>
        <article class="left">
          <p></p>
          <p>Daily Budget:</p>
          <p>Days Remaining</p>
          <p>Money Remanining</p>
          <p></p>
        </article>
        <article class="right">
          <p></p>
          <p>{{moneyPerDay}}💰</p>
          <p>{{daysToSalary}}</p>
          <p>{{availableSumm}}💰</p>
          <p></p>
        </article>
      </section>
    </article>
  </section>
</template>

<script>
import storage from "../../services/localstorageService";

export default {
  name: "Home",
  data() {
    const [err, data] = storage.homeCalculation();

    if (err || data.daysToSalary < 1) this.$router.push("/new");

    return data;
  },
  methods: {
    add: function() {
      this.$router.push("/add");
    },
    editBudget: function() {
      this.$router.push("/new");
    }
  }
};
</script>

<style lang='scss' src='./home.component.scss'>
</style>
