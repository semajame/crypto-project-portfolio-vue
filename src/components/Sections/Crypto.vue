<template>
  <section class="px-[1.5rem] pb-[10rem]">
    <h2 class="text-[3rem] text-white">Market Update</h2>

    <div class="overflow-y-auto">
      <table v-if="coinData" class="w-full mt-12 border">
        <thead>
          <tr
            class="bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-2xl text-center text-white"
          >
            <th class="p-5">{{ coin }}</th>
            <th>{{ price }}</th>
            <th>{{ change }}</th>
            <th>{{ market }}</th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="(coin, index) in coinData"
            :key="index"
            class="border text-center text-white"
          >
            <td class="p-5 coin text-md flex items-center gap-3 max-sm:text-sm">
              <div class="w-[50px] h-[50px]">
                <img :src="coin.image" alt="Coin Image" />
              </div>
              {{ coin.name }}
            </td>
            <td class="price text-md max-sm:text-sm">
              {{ "$ " + coin.current_price.toFixed(2) }}
            </td>
            <td class="change text-md max-sm:text-sm">
              <div v-if="coin.price_change_24h < 0" class="text-red-500">
                {{ coin.price_change_24h.toFixed(2) + "%" }}
              </div>
              <div v-else class="text-green-500">
                {{ coin.price_change_24h.toFixed(2) + "%" }}
              </div>
            </td>
            <td class="market text-md max-sm:text-sm">
              {{ "$ " + coin.market_cap.toLocaleString() }}
            </td>
          </tr>
        </tbody>
      </table>
      <div v-else class="loader mx-auto mt-[10rem]"></div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      coinData: null,
      coin: "Coin",
      price: "Price",
      change: "24h Change",
      market: "Market Cap",
    };
  },
  async mounted() {
    try {
      const apiLink =
        "https://api.coingecko.com/api/v3/coins/markets?vs_currency=usd&order=market_cap_desc&per_page=50&page=1&sparkline=false&price_change_percentage=24h";

      const response = await fetch(apiLink, {
        method: "GET",
        headers: {
          "Content-Type": "application/json",
        },
      });

      if (!response.ok) {
        throw new Error(`Network response was not ok: ${response.statusText}`);
      }

      const data = await response.json();
      this.coinData = data; // Set data to the component's property
    } catch (error) {
      // Handle errors
      console.error("Error fetching or processing data:", error);
    }
  },
};
</script>

<style></style>
