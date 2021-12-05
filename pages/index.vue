<template>
  <div>
    <v-app-bar
      shaped
      prominent
      color="grey"
    >
      <v-avatar
        class="mr-3"
        color="grey lighten-5"
        size="90"
      >
        <v-img
          contain
          max-height="90%"
          src="http://nncignorerlaloi.free.fr/wp-content/uploads/2019/10/cropped-logo.png"
        />
      </v-avatar>
      <v-flex>
        <v-toolbar-title
          class="font-weight-black headline titre"
        >
          Nul n'est censé ignorer la loi
        </v-toolbar-title>
        <v-toolbar-title>Nemo censetur ignorare lege</v-toolbar-title>
      </v-flex>
    </v-app-bar>

    <v-content
      fill-height
    >
      <section id="hero">
        <v-row
          fill-height
          no-gutters
        >
          <v-img
            width="100%"
            :min-height="'calc(100vh - ' + $vuetify.application.top + 'px)'"
            src="http://nncignorerlaloi.free.fr/wp-content/uploads/2019/10/S0-Justice.jpg"
          >
            <v-theme-provider dark>
              <v-container
                fill-height
                no-gutters
              >
                <v-row
                  align="center"
                  class="white--text"
                  justify="center"
                >
                  <v-col
                    class="white--text text-center"
                    cols="12"
                    tag="h1"
                  >
                    <span
                      :class="[$vuetify.breakpoint.smAndDown ? 'display-1' : 'display-2']"
                      class="font-weight-light"
                    >
                      Avoir des droits c'est bien.
                    </span>

                    <br>

                    <span
                      :class="[$vuetify.breakpoint.smAndDown ? 'display-3': 'display-4']"
                      class="font-weight-black"
                    >
                      Les connaitre c'est mieux !!
                    </span>
                  </v-col>

                  <v-btn
                    class="align-self-end"
                    color="red"
                    fab
                    @click="$vuetify.goTo('#about-me')"
                  >
                    <v-icon>mdi-chevron-double-down</v-icon>
                  </v-btn>
                </v-row>
              </v-container>
            </v-theme-provider>
          </v-img>
        </v-row>
      </section>

      <section id="about-me">
        <div class="py-12" />

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">
            Nul n'est censé ignorer la loi
          </h2>

          <v-responsive
            class="mx-auto mb-8"
            width="56"
          >
            <v-divider class="mb-1" />

            <v-divider />
          </v-responsive>

          <v-responsive
            class="mx-auto title font-weight-light mb-8"
            max-width="900"
          >
            En théorie, il est vrai que nul n'est censé ignorer la loi. Mais la réalité est (très) loin d'être aussi simple. Avec plus de 70 codes en vigueur sur le territoire, le citoyen ne peut, bien evidemment pas tout connaitre de la loi. Même les professionnlles ne connaissent pas tout de la loi.
          </v-responsive>

          <v-avatar
            class="elevation-12 mb-12"
            size="128"
          >
            <v-img src="http://nncignorerlaloi.free.fr/wp-content/uploads/2019/10/cropped-logo.png" />
          </v-avatar>

          <div />

          <v-btn
            color="yellow"
            href="https://www.youtube.com/channel/UC7hohh4A1O1ueLvHSqixmzA"
            target="_blank"
            outlined
            large
          >
            <span class="yellow--text text--darken-1 font-weight-bold">
              La chaine youtube
            </span>
          </v-btn>
        </v-container>

        <div class="py-12" />
      </section>

      <section
        id="features"
        class="grey lighten-3"
      >
        <div class="py-12" />

        <v-container class="text-center">
          <h2 class="display-2 font-weight-bold mb-3">
            NEWS OF THE WORLD
          </h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1" />

            <v-divider />
          </v-responsive>

          <v-row>
            <v-col
              v-for="({ icon, title, text }, i) in features"
              :key="i"
              cols="12"
              md="4"
            >
              <v-card
                class="py-12 px-4"
                color="grey"
                flat
              >
                <v-theme-provider dark>
                  <div>
                    <v-avatar
                      color="primary"
                      size="88"
                    >
                      <v-icon
                        large
                        v-text="icon"
                      />
                    </v-avatar>
                  </div>
                </v-theme-provider>

                <v-card-title
                  class="justify-center font-weight-black text-uppercase"
                  v-text="title"
                />

                <v-card-text
                  class="subtitle-1"
                  v-text="text"
                />
              </v-card>
            </v-col>
          </v-row>
        </v-container>

        <div class="py-12" />
      </section>

      <section id="stats">
        <v-parallax
          :height="$vuetify.breakpoint.smAndDown ? 700 : 500"
          src="http://2.bp.blogspot.com/_mkUEVRFknd0/R7Nvhj4yKeI/AAAAAAAABb4/-nQY0eQ0DgY/S1600-R/ddhc1.jpg"
        >
          <v-container fill-height>
            <v-row class="mx-auto">
              <v-col
                v-for="[value, title] of stats"
                :key="title"
                cols="12"
                md="3"
              >
                <div class="text-center">
                  <div
                    class="display-3 font-weight-black mb-4"
                    v-text="value"
                  />

                  <div
                    class="title font-weight-regular text-lowercase"
                    v-text="title"
                  />
                </div>
              </v-col>
            </v-row>
          </v-container>
        </v-parallax>
      </section>

      <section id="blog">
        <div class="py-12" />

        <v-container>
          <h2 class="display-2 font-weight-bold mb-3 text-uppercase text-center">
            Blog
          </h2>

          <v-responsive
            class="mx-auto mb-12"
            width="56"
          >
            <v-divider class="mb-1" />

            <v-divider />
          </v-responsive>

          <v-row>
            <v-col
              v-for="({ src, text, title }, i) in articles"
              :key="i"
              cols="12"
              md="4"
            >
              <v-img
                :src="src"
                class="mb-4"
                height="275"
                max-width="100%"
              />

              <h3
                class="font-weight-black mb-4 text-uppercase"
                v-text="title"
              />

              <div
                class="title font-weight-light mb-5"
                v-text="text"
              />

              <v-btn
                class="ml-n4 font-weight-black"
                text
              >
                on est ici
              </v-btn>
            </v-col>
          </v-row>
        </v-container>
      </section>
    </v-content>

    <v-footer
      class="justify-center"
      color="#292929"
      height="100"
    >
      <div class="title font-weight-light grey--text text--lighten-1 text-center">
        &copy; {{ (new Date()).getFullYear() }} — Made with 💜 by Devon Thefloor
      </div>
    </v-footer>
  </div>
</template>

<script>
export default {
  data () {
    return {
      articles: [
        {
          src: 'https://images.unsplash.com/photo-1423784346385-c1d4dac9893a?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80',
          title: 'Mobile first & Responsive',
          text: 'Phasellus lorem enim, luctus ut velit eget, convallis egestas eros. Sed ornare ligula eget tortor tempor, quis porta tellus dictum.'
        },
        {
          src: 'https://images.unsplash.com/photo-1475938476802-32a7e851dad1?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1950&q=80',
          title: 'Think outside the box',
          text: 'Nam ut leo ipsum. Maecenas pretium aliquam feugiat. Aenean vel tempor est, vitae tincidunt risus. Sed sodales vestibulum nibh.'
        },
        {
          src: 'https://images.unsplash.com/photo-1416339442236-8ceb164046f8?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1892&q=80',
          title: 'Small changes, big difference',
          text: 'Vestibulum in dictum velit, in rhoncus nibh. Maecenas neque libero, interdum a dignissim in, aliquet vitae lectus. Phasellus lorem enim, luctus ut velit eget.'
        }
      ],
      features: [
        {
          icon: 'mdi-account-group-outline',
          title: 'Vibrant Community',
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto cupiditate sint possimus quidem atque harum excepturi nemo velit tempora! Enim inventore fuga, qui ipsum eveniet facilis obcaecati corrupti asperiores nam'
        },
        {
          icon: 'mdi-update',
          title: 'Frequent Updates',
          text: 'Sed ut elementum justo. Suspendisse non justo enim. Vestibulum cursus mauris dui, a luctus ex blandit. Lorem ipsum dolor sit amet consectetur adipisicing elit. qui ipsum eveniet facilis obcaecati corrupti consectetur adipisicing elit.'
        },
        {
          icon: 'mdi-shield-outline',
          title: 'Long-term Support',
          text: 'Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto cupiditate sint possimus quidem atque harum excepturi nemo velit tempora! Enim inventore fuga, qui ipsum eveniet facilis obcaecati corrupti asperiores nam'
        }
      ],
      stats: [
        ['5,1k', 'Abonnés sur youtube'],
        ['108', 'Vidéos']
      ]
    }
  }
}
</script>

<style>
.titre {
  overflow: auto;
}
</style>
