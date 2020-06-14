<template>
  <div class="expense-container">
    <div class="total-cost">
      <h1>Calculated Trip Cost: {{ totalTripCost }}</h1>
    </div>

    <div class="expense-item-container">
      <div class="expense-item hotel"></div>
      <div class="input-row">
        <label>
          Hotel Name:
          <br />
          <input id="hotel-name" />
        </label>
      </div>
      <div class="input-row">
        <label>
          Hotel Cost:
          <br />
          <input id="hotel-cost" v-model.number="hotelCostInit" placeholder="0" type="number" />
        </label>
      </div>
    </div>

    <div class="expense-item-container">
      <h1>Flights</h1>
      <div class="expense-item flights"></div>
      <div class="input-row">
        <label>
          Flight Cost:
          <br />
          <input id="flight-cost" v-model.number="flightCostInit" placeholder="0" type="number" />
        </label>
      </div>
    </div>

    <div class="expense-item-container">
      <h1>Car Rental</h1>
      <div class="expense-item car"></div>
    </div>

    <div class="expense-item-container">
      <h1>Food and Drink</h1>
      <div class="expense-item food"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data: function() {
    return {
      hotelCostInit: 0,
      flightCostInit: 0
    };
  },
  computed: {
    hotelCostComputed: function() {
      if (this.hotelCostInit !== null && this.hotelCostInit.toString() === "") {
        return 0;
      } else {
        return this.hotelCostInit;
      }
    },
    flightCostComputed: function() {
      if (
        this.flightCostInit !== null &&
        this.flightCostInit.toString() === ""
      ) {
        return 0;
      } else {
        return this.flightCostInit;
      }
    },
    totalTripCost: function() {
      return (
        parseInt(this.hotelCostComputed) + parseInt(this.flightCostComputed)
      );
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.expense-container {
  display: flex;
  align-items: center;
  flex-direction: column;
}

.expense-item {
  width: 200px;
  height: 200px;
  margin: 0 0 40px 0;
  border-radius: 12px;
  background-repeat: no-repeat;
  background-size: 50%;
  background-position: center;
  box-shadow: 0 1px 2px rgba(0, 0, 0, 0.07), 0 2px 4px rgba(0, 0, 0, 0.07),
    0 4px 8px rgba(0, 0, 0, 0.07), 0 8px 16px rgba(0, 0, 0, 0.07),
    0 16px 32px rgba(0, 0, 0, 0.07), 0 32px 64px rgba(0, 0, 0, 0.07);
  padding: 0.75rem;
  transition: 0.3s;
}
.expense-item:hover {
  transform: scale(1.03);
  box-shadow: 0 1px 1px rgba(0, 0, 0, 0.12), 0 2px 2px rgba(0, 0, 0, 0.12),
    0 4px 4px rgba(0, 0, 0, 0.12), 0 8px 8px rgba(0, 0, 0, 0.12),
    0 16px 16px rgba(0, 0, 0, 0.12);
}

.hotel {
  background-color: #ffd3d3;
  background-image: url(https://img.icons8.com/officel/480/000000/5-star-hotel.png);
}

.flights {
  background-color: #d3daff;
  background-image: url("https://img.icons8.com/color/480/000000/airplane-front-view.png");
}

.car {
  background-color: #e5ffe7;
  background-image: url("https://img.icons8.com/officel/480/000000/carpool.png");
}

.food {
  background-color: #fff0ba;
  background-image: url("https://img.icons8.com/color/480/000000/food-and-wine.png");
}

/*# sourceMappingURL=App.css.map */
</style>
