
<template>
    <base-card>
        <base-button @click="setSelectedTab('stored-resources')" type="button" :mode="isResourcesTabSelected">Resources</base-button>
        <base-button @click="setSelectedTab('add-resource')" type="button" :mode="isAddResourceTabSelected">Add Resource</base-button>
    </base-card>

    <component :is="selectedTab"></component>
</template>

<script>
import StoredResources from './StoredResources.vue';
import AddResource from './AddResource.vue';

export default {
    components: {
        StoredResources,
        AddResource
    },
    provide() {
        return {
            resources: this.resources,
            removeResource: this.removeResource
        }
    },
    data() {
        return {
            selectedTab: 'stored-resources',
            resources: [
                {
                    id: 'official-guide',
                    title: 'Ofiicial Guide',
                    description: 'The Official Vue.js documentation',
                    link: 'https://vuejs.org'
                },
                {
                    id: 'google',
                    title: 'Google',
                    description: 'Learn how to google',
                    link: 'https://google.com'
                },
            ]
        }
    },
    mounted() {
        this.resources.map(r => console.log(`id: ${r.id}`));
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        },
        removeResource(id) {
            const index = this.resources.indexOf(id);
            this.resources.splice(index, 1);
        }
    },
    computed: {
        isResourcesTabSelected() {
            return this.selectedTab === 'stored-resources' ? null : 'flat';
        },
        isAddResourceTabSelected() {
            return this.selectedTab === 'add-resource' ? null : 'flat';
        }
    }
}
</script>
