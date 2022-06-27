
<template>
    <base-button @click="setSelectedTab('resources')" type="button" :mode="isResourcesTabSelected">Resources</base-button>
    <base-button @click="setSelectedTab('add-resource')" type="button" :mode="isAddResourceTabSelected">Add Resource</base-button>
</template>

<script>

export default {
    data() {
        return {
            selectedTab: 'resources'
        }
    },
    methods: {
        setSelectedTab(tab) {
            this.selectedTab = tab;
        }
    },
    computed: {
        isResourcesTabSelected() {
            return this.selectedTab === 'resources' ? null : 'flat';
        },
        isAddResourceTabSelected() {
            return this.selectedTab === 'add-resource' ? null : 'flat';
        }
    }
}
</script>
