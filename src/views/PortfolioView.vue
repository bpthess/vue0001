<template>
  <HeaderCont />
  <main id="main">
    <section class="port__cont">
      <TitleCont name1="Portfolio" name2="reference" />
      <div class="container">
        <div class="port__inner">
          <ariticle class="port__item" v-for="port in ports" :key="port.id">
            <figure>
              <a href="port.link" target="_blank">
                <img :src="port.image" :alt="port.title" />
              </a>
            </figure>
            <div class="text">
              <h3>{{ port.title }}</h3>
              <p>{{ port.catagory }}</p>
            </div>
          </ariticle>
        </div>
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
import { ref } from "vue";

export default {
  components: {
    HeaderCont,
    FooterCont,
    TitleCont,
    ContactCont,
  },
  setup() {
    const ports = ref([]);

    const Portfolios = () => {
      var requestOptions = {
        method: "GET",
        redirect: "follow",
      };

      fetch(
        "https://webstoryboy.github.io/dothome1/portfolio.json",
        requestOptions
      )
        .then((response) => response.json())
        .then((data) => (ports.value = data.data.ports))
        .catch((error) => console.log("error", error));
    };
    console.log(ports);
    Portfolios();

    return {
      ports,
      Portfolios,
    };
  },
};
</script>

<style lang="scss" scoped>
.port__cont {
  background-color: var(--dark_bg);
}
.port__inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  flex-wrap: wrap;
}
.port__item {
  flex: 1 1 30%;
  margin: 1%;

  .text {
    padding: 1.4rem;
    background-color: #d0d0d0;

    h3 {
      color: var(—white);
      font-family: var(--main_font);
      font-size: 2.6rem;
      line-height: 1;
      padding-top: 0.2em;
      text-transform: uppercase;
    }
    p {
      color: var(—white);
      font-family: var(--sub_font);
    }
  }
}
</style>
