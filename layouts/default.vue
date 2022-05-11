 <template>
  <v-app dark>
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      app
      permanent
      class="transparent"
    >
      <v-list expand>

          <template v-for="nav_list in nav_lists">
            <v-list-item
              v-if="!nav_list.lists"
              :to="nav_list.link"
              :key="nav_list.name"
              
            >
            <v-list-item-content>
              <v-list-item-title v-text="nav_list.name"></v-list-item-title>
            </v-list-item-content>
            </v-list-item>

            <v-list-group
              v-else
              no-action
              :key="nav_list.name"
              :value="true"
              :append-icon="null"
            >
              <template v-slot:activator>

                <!-- <v-list-item-avatar>
                  <v-icon left color="red">mdi-star</v-icon>
                 </v-list-item-avatar> -->

                <v-list-item-content>
                  <v-list-item-title v-text="nav_list.name"></v-list-item-title>
                </v-list-item-content>
              </template>


              <v-list-group
                v-for="child in nav_list.lists"
                no-action
                :append-icon="null"
                :prepend-icon="null"
                :value ="true"
                :key="child.name"
                :to="child.link"
                sub-group
                :ripple="true"
              >

                <template v-slot:activator>
                <v-list-group-item>

                  <v-list-item-content>
                    <v-list-item-title v-text="child.name"></v-list-item-title>
                  </v-list-item-content>
                </v-list-group-item>
                </template>

                <!-- class="v-list-item__icon v-list-group__header__prepend-icon" -->

                <v-list-item
                  v-for="work in child.lists"
                  :key="work.name"
                  :to="work.link"
                  :prepend-icon="null"
                  :append-icon="null"

                >
                  <v-list-item-title v-text="work.name"></v-list-item-title>
                </v-list-item>
              </v-list-group>
            </v-list-group>
          </template>

      </v-list>

</v-navigation-drawer>

    <v-main>
      <v-container>
        <v-row>
          <v-col
            v-for="n in 24"
            :key="n"
            cols="4"
          >
            <v-card height="200"></v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
  methods:{
          menu_close(){
            this.nav_lists.forEach( nav_list => nav_list.active = false)
          }
        },
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      nav_lists: [
        {
          name: 'Home',
          link: '/',
        },
        {
          name: 'Profile',
          link: '/profile',
        },
        {
          name: 'Works',
          link: '/works',
          active: false,
          lists: [
            {
              name: 'Artworks',
              link: '/interactive',
              lists: [
                {
                  name: 'Virtual Hallucinogen',
                  link: '/virtual_hallucinogen',
                },
                {
                  name: "It's all here.",
                  link: '/its_all_here',
                },
                {
                  name: "sphere",
                  link: '/sphere',
                },
                {
                  name: "共感覚をモチーフとしたアプリケーションの制作",
                  link: '/sync_app',
                },
              ],
            },
            {
              name: 'Video',
              link: '/videos',
              lists: [
                {
                  name: 'Visual Jockey',
                  link: '/visual_jockey',
                },
                {
                  name: 'Motion Graphics',
                  link: '/motion_raphics',
                },
                {
                  name: 'Direction & Shooting',
                  link: '/live_action',
                },
              ],
            },
          ],
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    }
  },
}
</script> 

