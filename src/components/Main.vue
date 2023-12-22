<template>
  <header
    class="flex justify-between items-center p-5 fixed top-0 left-0 right-0 z-10 bg-[#000000c5] max-w-[1440px] m-auto backdrop-blur-sm"
  >
    <div>
      <a href="/" v-scrollto="'home'">
        <img :src="logo" alt="Crypto Logo" class="w-[250px]" />
      </a>
    </div>
    <div>
      <nav>
        <ul class="flex">
          <li
            v-for="(item, index) in routerLinks"
            :key="index"
            class="px-3 font-bold text-xs tracking-wider"
            v-scrollto="item.scrollTo"
          >
            <a class="text-white hover:text-[#36316e] text-sm cursor-pointer">
              {{ item.link }}
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
  <main class="pb-[5rem] pt-[10rem] relative" id="home">
    <div>
      <h1
        class="text-white font-extrabold text-6xl w-[800px] mt-7 mb-10 mx-auto text-center"
      >
        {{ header }}
      </h1>

      <p
        class="text-slate-300 font-sans my-5 text-xl text-center w-[800px] mx-auto"
      >
        {{ paragraph }}
      </p>

      <div class="flex gap-8 my-8 justify-center mt-[4rem]">
        <button
          class="bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-white font-bold rounded-[10px] uppercase tracking-wider text-sm px-8 py-6"
        >
          {{ getStarted }}
        </button>
        <button
          class="bg-[#282454] text-white font-bold rounded-[10px] uppercase tracking-wider text-sm px-8 py-6"
        >
          {{ learnMore }}
        </button>
      </div>
    </div>

    <div class="relative">
      <img
        :src="heroBackground"
        alt="Hero Background"
        class="left-0 right-0 -z-10 top-0 w-full h-[500px]"
      />
    </div>
  </main>
  <Featured />
  <Crypto id="market" />
  <NewEra id="about" />
  <JoinUs id="join" />
</template>

<script>
import Contact from "@/components/Sections/Contact.vue";
import Crypto from "@/components/Sections/Crypto.vue";
import NewEra from "@/components/Sections/NewEra.vue";
import Featured from "@/components/Sections/Featured.vue";
import JoinUs from "@/components/Sections/JoinUs.vue";
import heroBackground from "../assets/images/hero-background.webp";

const scrollToDirective = {
  mounted(el, binding) {
    el.addEventListener("click", (event) => {
      event.preventDefault();
      const targetId = binding.value;
      const targetElement = document.getElementById(targetId);

      if (targetElement) {
        const offset = 100; // You can adjust this value for your desired margin or padding
        const scrollTo = targetElement.offsetTop - offset;

        window.scrollTo({
          behavior: "smooth",
          top: scrollTo,
        });
      }
    });
  },
};

export default {
  components: {
    Crypto,
    NewEra,
    JoinUs,
    Contact,

    Featured,
  },

  directives: {
    scrollto: scrollToDirective,
  },

  data() {
    return {
      logo: "https://assets-global.website-files.com/62ea94aa50fb59ad3ea476f0/62ead07c4e3c0613c01dd91c_logo-cryptocurrency-template.svg",

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

      header: "Trade and Track crypto like never before",
      paragraph:
        " Lorem ipsum dolor sit amet, consectetur adipiscing elit. Feugiat nulla suspendisse tortor aenean dis placerat.",
      getStarted: "Get Started",
      learnMore: "Learn More",
      heroBackground: heroBackground,
      laptop:
        "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac9aa80f78095f831b055d_image-home-hero-1-crypto-template-p-1600.png",
      phone:
        "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac96501854f8e4e061e9c6_image-home-hero-2-crypto-template.png",
    };
  },
};
</script>

<style></style>
