<template>
  <HeaderCont />
  <main id="main">
    <section class="main__cont">
      <TitleCont name1="introduce" name2="me" />
      <div class="main__inner">
        <!-- <div v-for="title in titles" v-bind:key="title.text">
          {{ title.text }}
        </div> -->
      </div>
      <ContactCont />
    </section>
  </main>
  <FooterCont />
</template>

<script>
import HeaderCont from "@/components/HeaderCont.vue";
import FooterCont from "@/components/FooterCont.vue";
import TitleCont from "@/components/TitleCont.vue";
import ContactCont from "@/components/ContactCont.vue";

export default {
  components: {
    HeaderCont,
    FooterCont,
    TitleCont,
    ContactCont,
  },

  data: function () {
    return {
      titles: [
        { text: "we provide" },
        { text: "visual coding" },
        { text: "solution" },
        { text: "for you webs" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.main__cont {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  background: var(--dark_bg);
  .main__inner {
    font-size: 10vw;
    line-height: 0.85;
    font-family: var(--main_font);
    color: var(--white);
    text-transform: uppercase;
  }
}
</style>
