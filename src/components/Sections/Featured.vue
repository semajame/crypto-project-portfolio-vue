<template>
  <section class="pb-[10rem]">
    <div>
      <h2 class="text-center text-md font-bold text-slate-300 uppercase p-10">
        Crypto app has been featured on
      </h2>

      <div class="flex items-center justify-around">
        <img
          v-for="(items, index) in companyImg"
          :key="index"
          :src="items.img"
          alt="Company Image"
          class="w-[180px]"
        />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      companyImg: [
        {
          img: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac237395a566b8e10a71a3_logo-company-1-crypto-template.svg",
        },
        {
          img: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac2373a193a30ee7f7ec90_logo-company-2-crypto-template.svg",
        },
        {
          img: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac23736626902953e36765_logo-company-3-crypto-template.svg",
        },
        {
          img: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac23739ac6bbe17747ebd3_logo-company-4-crypto-template.svg",
        },
        {
          img: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac2374cafaca6db67472ea_logo-company-5-crypto-template.svg",
        },
      ],
    };
  },
};
</script>

<style></style>
