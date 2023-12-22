<template>
  <section class="pt-[5rem]">
    <div class="text-center">
      <div class="flex justify-center gap-10 items-center">
        <img
          :src="bitcoin"
          alt="Bitcoin Image"
          class="w-[100px] h-[100px] animate-slow-bounce"
        />
        <div>
          <h2 class="text-white text-8xl uppercase font-normal">
            {{ join }}
            <span
              class="block font-bold bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-[#6248ff] text-transparent bg-clip-text"
            >
              {{ discord }}
            </span>
          </h2>
        </div>
        <img
          :src="ethereum"
          alt="Ethereum Image"
          class="w-[100px] h-[100px] animate-slow-bounce"
        />
      </div>

      <div>
        <p class="text-slate-300 text-xl my-10">
          {{ paragraph }}
        </p>
        <button
          class="block font-bold bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-white p-5 rounded-md mt-5 mx-auto"
        >
          {{ button }}
        </button>
      </div>
    </div>
  </section>
</template>

<script>
import bitcoin from "@/assets/images/bitcoin.png";
import ethereum from "@/assets/images/ethereum.png";
export default {
  data() {
    return {
      join: "Join us via",
      discord: "Discord",
      paragraph: "Invest and manage all your crypto at one place.",
      button: "Join via Discord",
      bitcoin: bitcoin,
      ethereum: ethereum,
    };
  },
};
</script>

<style></style>
