<template>
    <nav>
        <v-app-bar flat app class="grey lighten-4">
            <v-app-bar-nav-icon
                class="grey--text"
                @click="drawer = !drawer"
            ></v-app-bar-nav-icon>
            <v-toolbar-title class="text-uppercase grey--text">
                <span>Todo</span>
                <span class="font-weight-bold">ninja</span>
            </v-toolbar-title>
            <v-spacer />
            <v-btn depressed>
                <span>Sign Out</span>
                <v-icon right>mdi-exit-to-app</v-icon>
            </v-btn>
        </v-app-bar>

        <v-navigation-drawer app v-model="drawer" color="primary">
            <v-list dense>
                <v-list-item-group v-model="selectedItem">
                    <v-list-item
                        v-for="(item, i) in links"
                        :key="i"
                        router
                        :to="item.route"
                    >
                        <v-list-item-icon>
                            <v-icon v-text="item.icon" class="white--text" />
                        </v-list-item-icon>
                        <v-list-item-content>
                            <v-list-item-title
                                v-text="item.text"
                                class="white--text"
                            />
                        </v-list-item-content>
                    </v-list-item>
                </v-list-item-group>
            </v-list>
        </v-navigation-drawer>
    </nav>
</template>

<script>
export default {
    data: () => ({
        drawer: true,
        selectedItem: 0,
        links: [
            { text: 'Dashboard', icon: 'mdi-view-dashboard', route: '/' },
            { text: 'My Projects', icon: 'mdi-folder', route: '/projects' },
            { text: 'Team', icon: 'mdi-account', route: '/team' }
        ]
    })
}
</script>
