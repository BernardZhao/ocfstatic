<template>
  <Layout>
    <section class="section">
      <div class="container">
        <div class="content">
          <h1 class="title is-1">About Us</h1>
          <div class="columns is-8 is-variable">
            <div class="column is-half">
              <h2 class="subtitle">What We Do</h2>
              <p class="is-size-5">
                We're a student organization dedicated to providing free
                computing for all UC Berkeley students, faculty, and staff. We
                run a super awesome computer lab on southside, have a wicked set
                of servers for staff to play on, and provide cool services to
                the Berkeley community.
              </p>
            </div>
            <div class="column is-half">
              <h2 class="subtitle">Staff Meetings</h2>
              <p class="is-size-5">
                OCF Staff meet to discuss technology, learn from each other, and
                work on OCF projects. Drop-in visitors are always welcome,
                especially those interested in joining the staff team!
              </p>
              <p class="is-size-4">
                <strong>When:</strong> Every Monday at 8:10pm
              </p>
              <p class="is-size-4">
                <strong>Where: </strong>
                <a href="https://ocf.io/meet">Google Meet</a>
              </p>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="is-divider"></div>
    <section class="section">
      <div class="container">
        <div class="columns is-vcentered reverse-row-order">
          <div class="column is-half">
            <transition name="fade" mode="out-in">
              <img
                :key="servicesImages[servicesActiveImage]"
                :src="servicesImages[servicesActiveImage]"
                data-toggle="tooltip"
                width="800"
                height="600"
                data-placement="bottom"
                title="goTop"
                alt=""
              />
            </transition>
          </div>
          <div class="column is-half">
            <div class="columns is-centered is-vcentered">
              <div class="column is-three-quarters">
                <div class="content">
                  <h2 class="title is-2 has-text-centered">
                    Services We Provide
                  </h2>

                  <p
                    class="button card box is-white is-medium"
                    :class="{ 'active-card': servicesActiveImage === 0 }"
                    @click="servicesActiveImage = 0"
                  >
                    Web &amp; Email Hosting
                  </p>
                  <p
                    class="button card box is-white is-medium"
                    :class="{ 'active-card': servicesActiveImage === 1 }"
                    @click="servicesActiveImage = 1"
                  >
                    UNIX Shell Accounts
                  </p>
                  <p
                    class="button card box is-white is-medium"
                    :class="{ 'active-card': servicesActiveImage === 2 }"
                    @click="servicesActiveImage = 2"
                  >
                    Free Printing for Members
                  </p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="is-divider"></div>
    <section class="section">
      <div class="container">
        <div class="columns is-vcentered">
          <div class="column is-half">
            <g-image
              src="~/assets/penguins_placeholder.jpg"
              width="800"
              height="600"
            />
          </div>
          <div class="column is-half">
            <div class="columns is-centered is-vcentered">
              <div class="column is-three-quarters">
                <h2 class="title is-2 has-text-centered">
                  Joining the OCF is an awesome way to learn!
                </h2>
                <h4 class="title is-4">
                  We love talking tech and learning new things.
                </h4>
                <p>
                  We use our weekly board meetings and staff hours not just to
                  make decisions, but also to learn more about *nix and free
                  software.
                </p>
                <h4 class="title is-4">
                  We're totally open and super-inclusive!
                </h4>
                <p>
                  Our members have a wide range of majors and technical
                  backgrounds. There are tons of ways to learn and have fun!
                </p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>
    <div class="is-divider"></div>
    <!--- The timeline -->

    <section class="section has-text-centered">
      <div class="container">
        <h1 class="title">History</h1>
        <history />
      </div>
    </section>
  </Layout>
</template>

<script>
import History from "~/components/History.vue";
export default {
  metaInfo: {
    title: "About Us"
  },
  components: {
    History
  },
  data() {
    return {
      servicesActiveImage: 0,
      servicesImages: [
        "/assets/img/cloud.jpg",
        "/assets/img/unix-shell.jpg",
        "/assets/img/printer.jpg"
      ]
    };
  }
};
</script>
<style scoped>
p.card {
  transition: transform 0.6s;
  width: 100%;
}
.active-card {
  transform: translateX(1.75em);
}
.reverse-row-order {
  flex-direction: row-reverse;
}
</style>
