<template>
    
    <v-app id="inspire">

        <v-navigation-drawer v-model="drawer"
                             app dark>
            <!--  -->

            <v-card>
                <v-list>
                    <v-list-group v-for="item in navItems"
                                  :key="item.title"
                                  v-model="item.active"
                                  :prepend-icon="item.action"
                                  no-action>
                        <template v-slot:activator>
                            <v-list-item-content>
                                <v-list-item-title v-text="item.title"></v-list-item-title>
                            </v-list-item-content>
                        </template>

                        <v-list-item v-for="child in item.items"
                                     :key="child.title">
                            <v-list-item-content>
                                <v-list-item-title v-text="child.title"></v-list-item-title>
                            </v-list-item-content>
                        </v-list-item>
                    </v-list-group>
                </v-list>
            </v-card>
        </v-navigation-drawer>

        <v-app-bar elevation="2" app dark>
            <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>

            <v-toolbar-title>Application</v-toolbar-title>

        </v-app-bar>
        
        <v-main>
            <template>
                <v-progress-linear value="15"></v-progress-linear>
            </template>
            <template>
                <v-card>
                    <v-container>
                        <v-row>
                            <v-col>
                                <v-tabs v-model="tab"
                                        dark>
                                    <v-tab v-for="item in tabItems"
                                           :key="item.tab">
                                        {{ item.tab }}
                                    </v-tab>
                                </v-tabs>

                                <v-tabs-items v-model="tab">
                                    <v-tab-item v-for="item in tabItems"
                                                :key="item.tab">
                                        <v-card flat>
                                            <template>
                                                <v-card>

                                                    

                                                    <v-list three-line>
                                                        
                                                        <template v-for="(item, index) in tabContentItems">

                                                            <v-subheader v-if="item.header"
                                                                         :key="item.header"
                                                                         v-text="item.header"></v-subheader>

                                                            <v-divider v-else-if="item.divider"
                                                                       :key="index"
                                                                       :inset="item.inset"></v-divider>

                                                            <v-list-item v-else
                                                                         :key="item.title">
                                                                <v-list-item-avatar>
                                                                    <v-img :src="item.avatar"></v-img>
                                                                </v-list-item-avatar>

                                                                <v-list-item-content>
                                                                    <v-list-item-title v-html="item.title"></v-list-item-title>
                                                                    <v-list-item-subtitle v-html="item.subtitle"></v-list-item-subtitle>
                                                                </v-list-item-content>
                                                            </v-list-item>

                                                        </template>
                                                    </v-list>

                                                </v-card>
                                            </template>
                                        </v-card>
                                    </v-tab-item>
                                </v-tabs-items>
                            </v-col>
                        </v-row>
                    </v-container>
                </v-card>
            </template>
        </v-main>
    </v-app>
</template>

<script>
    export default {
        data: () => ({
            drawer: null,
            navItems: [
                {
                    action: 'mdi-ticket',
                    items: [{ title: 'List Item' }],
                    title: 'Attractions',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    active: true,
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining',
                },
                {
                    action: 'mdi-school',
                    items: [{ title: 'List Item' }],
                    title: 'Education',
                },
                {
                    action: 'mdi-human-male-female-child',
                    items: [{ title: 'List Item' }],
                    title: 'Family',
                },
                {
                    action: 'mdi-bottle-tonic-plus',
                    items: [{ title: 'List Item' }],
                    title: 'Health',
                },
                {
                    action: 'mdi-briefcase',
                    items: [{ title: 'List Item' }],
                    title: 'Office',
                },
                {
                    action: 'mdi-tag',
                    items: [{ title: 'List Item' }],
                    title: 'Promotions',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining1',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining2',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining3',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining4',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining5',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining6',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining7',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining8',
                },
                {
                    action: 'mdi-silverware-fork-knife',
                    items: [
                        { title: 'Breakfast & brunch' },
                        { title: 'New American' },
                        { title: 'Sushi' },
                    ],
                    title: 'Dining9',
                }

            ],

            tab: null,
            tabItems: [
                { tab: 'One', content: 'Tab 1 Content' },
                { tab: 'Two', content: 'Tab 2 Content' },
                { tab: 'Three', content: 'Tab 3 Content' },
                { tab: 'Four', content: 'Tab 4 Content' },
                { tab: 'Five', content: 'Tab 5 Content' },
                { tab: 'Six', content: 'Tab 6 Content' },
                { tab: 'Seven', content: 'Tab 7 Content' },
                { tab: 'Eight', content: 'Tab 8 Content' },
                { tab: 'Nine', content: 'Tab 9 Content' },
                { tab: 'Ten', content: 'Tab 10 Content' },
            ],

            tabContentItems: [
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/1.jpg',
                    title: 'Brunch this weekend?',
                    subtitle: `<span class="text--primary">Ali Connors</span> &mdash; I'll be in your neighborhood doing errands this weekend. Do you want to hang out?`,
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/2.jpg',
                    title: 'Summer BBQ <span class="grey--text text--lighten-1">4</span>',
                    subtitle: `<span class="text--primary">to Alex, Scott, Jennifer</span> &mdash; Wish I could come, but I'm out of town this weekend.`,
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/3.jpg',
                    title: 'Oui oui',
                    subtitle: '<span class="text--primary">Sandra Adams</span> &mdash; Do you have Paris recommendations? Have you ever been?',
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/4.jpg',
                    title: 'Birthday gift',
                    subtitle: '<span class="text--primary">Trevor Hansen</span> &mdash; Have any ideas about what we should get Heidi for her birthday?',
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
                    title: 'Recipe to try',
                    subtitle: '<span class="text--primary">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
                    title: 'Recipe to try 1',
                    subtitle: '<span class="text--primary">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
                    title: 'Recipe to try 2',
                    subtitle: '<span class="text--primary">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
                },
                { divider: true, inset: true },
                {
                    avatar: 'https://cdn.vuetifyjs.com/images/lists/5.jpg',
                    title: 'Recipe to try 3',
                    subtitle: '<span class="text--primary">Britta Holt</span> &mdash; We should eat this: Grate, Squash, Corn, and tomatillo Tacos.',
                },
            ],

        }),
    }
</script>
