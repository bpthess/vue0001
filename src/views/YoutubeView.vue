<template>
  <HeaderCont />
  <main id="main">
    <section class="youtube__cont">
      <TitleCont name1="Youtube" name2="reference" />
      <div class="youtube__inner"></div>
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
};
</script>

<style lang="scss" scoped></style>
