<template>
  <footer
    class="flex justify-between items-center py-[5rem] max-w-[1440px] m-auto"
  >
    <!-- <img
      src="https://assets-global.website-files.com/62ea94aa50fb59ad3ea476f0/62eb0d1a7701f11342289a72_image-2-section-feature-cryptocurrency-template.svg"
      alt=""
      class="max-w-[250px] max-h-[250px] absolute -left-10 -z-10"
    /> -->
    <nav class="m-auto">
      <ul class="flex justify-center items-center gap-10 max-sm:gap-5">
        <li v-for="(items, index) in socialLinks" :key="index" class="p-2">
          <a :href="items.link" target="_blank">
            <img
              :src="items.img"
              :alt="items.name"
              class="w-[30px] h-[30px] invert"
          /></a>
        </li>
      </ul>

      <div class="text-white flex justify-center gap-10 mt-5">
        <a href=""> Privacy </a>
        <a href=""> Terms of Use </a>
      </div>
    </nav>

    <!-- <img
      src="https://assets-global.website-files.com/62ea94aa50fb59ad3ea476f0/62eb0d1aa521b81c53133cba_image-1-section-feature-cryptocurrency-template.svg"
      alt=""
      class="max-w-[250px] max-h-[250px] absolute -right-10 -z-10"
    />-->
  </footer>
</template>

<script>
import facebook from "@/assets/images/facebook-f.svg";
import instagram from "@/assets/images/instagram.svg";
import twitter from "@/assets/images/twitter.svg";
import youtube from "@/assets/images/youtube.svg";
import linkedin from "@/assets/images/linkedin-in.svg";
import footerbg from "@/assets/images/footer-bg.png";

export default {
  data() {
    return {
      logo: "https://assets-global.website-files.com/5f8f28722b0eae892596eb35/5fac14536bfe49d6412e1990_logo-crypto-template.svg",

      footerbg: footerbg,

      socialLinks: [
        {
          img: facebook,
          link: "https://www.facebook.com/",
          name: "Facebook Image",
        },
        {
          img: instagram,
          link: "https://www.instagram.com/",
          name: "Instagram Image",
        },
        {
          img: twitter,
          link: "https://www.twitter.com/",
          name: "Twitter Image",
        },
        {
          img: youtube,
          link: "https://www.youtube.com/",
          name: "Youtube Image",
        },
        {
          img: linkedin,
          link: "https://www.linkedin.com/",
          name: "Linkedin Image",
        },
      ],
    };
  },
};
</script>
