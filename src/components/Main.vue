<template>
  <header
    class="flex justify-between items-center p-5 fixed top-0 left-0 right-0 z-20 bg-[#000000c5] m-auto backdrop-blur-sm"
  >
    <div>
      <a href="/" v-scrollto="'home'">
        <img :src="logo" alt="Crypto Logo" class="w-[250px] max-sm:w-[200px]" />
      </a>
    </div>
    <div>
      <button class="hidden max-sm:block" id="openButton">
        <img :src="hamburger" alt="Hamburger Icon" class="w-[2rem] h-[2rem]" />
      </button>

      <nav>
        <ul
          class="flex items-center max-sm:hidden max-sm:absolute max-sm:bottom-0 max-sm:left-0 max-sm:flex-col max-sm:right-0 max-sm:top-0 max-sm:z-20 max-sm:h-[100vh] max-sm:overflow- max-sm:backdrop-blur-sm max-sm:text-center max-sm:items-stretch max-sm:bg-[#000000d0]"
        >
          <div class="flex justify-end pr-5">
            <button class="hidden max-sm:block max-sm:my-7" id="closeButton">
              <img :src="close" alt="Menu Close" class="w-[2rem] h-[2rem]" />
            </button>
          </div>

          <li
            v-for="(item, index) in routerLinks"
            :key="index"
            class="px-3 font-bold text-xs tracking-wider max-sm:px-0 max-sm:py-5"
            v-scrollto="item.scrollTo"
          >
            <a
              class="text-white hover:text-[#36316e] text-sm cursor-pointer max-sm:text-2xl"
            >
              {{ item.link }}
            </a>
          </li>
        </ul>
      </nav>
    </div>
  </header>
  <main class="pb-[5rem] pt-[8rem] relative" id="home">
    <div>
      <h1
        class="text-white font-extrabold w-[800px] clamp mt-7 mb-10 mx-auto text-center max-sm:w-full"
      >
        {{ header }}
      </h1>

      <p
        class="text-slate-300 font-sans my-5 text-xl w-[800px] text-center mx-auto px-3 max-sm:w-full max-sm:text-sm"
      >
        {{ paragraph }}
      </p>

      <div class="flex gap-8 my-8 justify-center mt-[4rem]">
        <button
          class="bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-white font-bold rounded-[10px] uppercase tracking-wider text-sm px-8 py-6 max-sm:px-7 max-sm:py-4 max-sm:text-[0.8rem]"
        >
          {{ getStarted }}
        </button>
        <button
          class="bg-[#282454] text-white font-bold rounded-[10px] uppercase tracking-wider text-sm px-8 py-6 max-sm:text-[0.8rem] max-sm:px-7 max-sm:py-4"
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
  <div class="max-w-[1440px] m-auto">
    <!-- <Featured /> -->
    <Crypto id="market" />
    <NewEra id="about" />
    <JoinUs id="join" />
  </div>
</template>

<script>
import Contact from "@/components/Sections/Contact.vue";
import Crypto from "@/components/Sections/Crypto.vue";
import NewEra from "@/components/Sections/NewEra.vue";
import Featured from "@/components/Sections/Featured.vue";
import JoinUs from "@/components/Sections/JoinUs.vue";
import heroBackground from "../assets/images/hero-background.webp";
import hamburger from "../assets/images/hamburger-menu.png";
import close from "../assets/images/close-menu.png";

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

  mounted() {
    const closeButton = document.querySelector("#closeButton");
    const openButton = document.querySelector("#openButton");
    const nav = document.querySelector("ul");

    openButton.addEventListener("click", () => {
      console.log("open");
      nav.classList.add("max-sm:block");
      nav.classList.remove("max-sm:hidden");
    });

    closeButton.addEventListener("click", () => {
      console.log("close");
      nav.classList.remove("max-sm:block");
      nav.classList.add("max-sm:hidden");
    });
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
      hamburger: hamburger,
      close: close,
      laptop:
        "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac9aa80f78095f831b055d_image-home-hero-1-crypto-template-p-1600.png",
      phone:
        "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac96501854f8e4e061e9c6_image-home-hero-2-crypto-template.png",
    };
  },
};
</script>

<style></style>
