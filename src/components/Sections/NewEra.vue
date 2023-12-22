<template>
  <section class="text-white p-10 pb-[10rem] max-sm:p-5 max-sm:pb-[10rem]">
    <div class="text-center">
      <h2 class="pb-10 eraclamp">
        {{ header }}
      </h2>
      <p class="p-10 text-md max-sm:p-0 max-sm:pb-10">
        {{ paragraph }}
      </p>
    </div>
    <div class="flex justify-around pt-10 max-sm:flex-col">
      <div
        class="flex flex-col justify-around max-sm:justify-center max-sm:gap-10"
      >
        <div v-for="(items, index) in headerLeft" :key="index">
          <h2 class="font-bold text-6xl max-sm:text-center">
            {{ items.header }}
            <span
              class="bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-[#6248ff] text-transparent bg-clip-text font-normal -ml-3"
              >{{ items.span }}</span
            >
          </h2>
          <p
            class="mt-2 w-[150px] text-slate-400 max-sm:text-center max-sm:m-auto"
          >
            {{ items.paragraph }}
          </p>
        </div>
      </div>
      <div>
        <img :src="imageGlobe" alt="Globe Image" class="w-[600px] h-[600px]" />
      </div>
      <div
        class="flex flex-col justify-around max-sm:gap-10 max-sm:justify-center"
      >
        <div v-for="(items, index) in headerRight" :key="index">
          <h2 class="font-bold text-6xl max-sm:text-center">
            {{ items.header }}

            <span
              class="bg-gradient-to-tr from-[#ac50ef] via-[#7059fb] to-[#2ecff6] text-[#6248ff] text-transparent bg-clip-text font-normal -ml-3"
              >{{ items.span }}</span
            >
          </h2>
          <p
            class="mt-2 w-[150px] text-slate-400 max-sm:text-center max-sm:m-auto"
          >
            {{ items.paragraph }}
          </p>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      header: " A new era of crypto investments has arrived",
      paragraph:
        " Lorem ipsum dolor sit amet, consectetur adipiscing elit elit, eget tristique metus, turpis vestibulum, pretium donec.",
      imageGlobe:
        "https://assets-global.website-files.com/62ea94aa50fb59ad3ea476f0/62ec4c4432e6651bfcee75a3_image-investments-cryptocurrency-template.svg",
      headerLeft: [
        {
          header: "250",
          span: "%",
          paragraph: "Investments growth year over year",
        },
        {
          header: "1K",
          span: "+",
          paragraph: "New investors joining every day",
        },
      ],

      headerRight: [
        {
          header: "30M",
          span: "+",
          paragraph: "Monthly active users on the app",
        },
        {
          header: "70",
          span: "+",
          paragraph: "Team members in our team",
        },
      ],
    };
  },
};
</script>
