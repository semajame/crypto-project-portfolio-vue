<template>
  <header
    class="flex justify-between items-center p-5 fixed top-0 left-0 right-0 z-10 bg-[#000000c5] max-w-[1440px] m-auto backdrop-blur-sm"
  >
    <div>
      <a href="/">
        <img :src="logo" alt="Crypto Logo" class="w-[120px]" />
      </a>
    </div>
    <div>
      <nav>
        <ul class="flex">
          <li
            v-for="(item, index) in routerLinks"
            :key="index"
            class="px-3 font-bold text-xs tracking-wider"
            :v-scrollto="item.scrollTo"
          >
            <a class="text-white hover:text-[#36316e] text-sm cursor-pointer">
              {{ item.link }}
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
</template>

<script>
export default {
  data() {
    return {
      logo: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac14536bfe49d6412e1990_logo-crypto-template.svg",

      routerLinks: [
        {
          scrollTo: "about",
          link: "About",
        },

        {
          scrollTo: "market",
          link: "Market",
        },
        {
          scrollTo: "join",
          link: "Join Us",
        },
      ],
    };
  },
};
</script>

<style></style>
