<script setup lang="ts">
import { FPageLayout, FResizePane, registerLayout, FPageHeader, FLogo } from "@fkui/vue";
import { XContextBar, XToolbar } from "./components";

registerLayout({
    name: "awesome-layout",
    areas: {
        header: {
            attachPanel: "none",
            direction: "column",
        },
        left: {
            attachPanel: "left",
            direction: "column",
        },
        contextbar: {
            attachPanel: "none",
            direction: "row",
        },
        toolbar: {
            attachPanel: "none",
            direction: "row",
        },
        content: {
            attachPanel: "none",
            direction: "column",
            scroll: true,
        },
        right: {
            attachPanel: "right",
            direction: "column",
        },
        footer: {
            attachPanel: "none",
            direction: "column",
        },
    },
});
</script>

<template>
    <f-page-layout layout="awesome-layout">
        <template #header>
            <header>
                <f-page-header>
                    Layout components testbed
                    <template #logo>
                        <f-logo size="small">Logo</f-logo>
                    </template>
                    <template #right> Namn Namnsson </template>
                </f-page-header>
            </header>
        </template>
        <template #contextbar> <x-context-bar></x-context-bar> </template>
        <template #toolbar>
            <x-toolbar></x-toolbar>
        </template>
        <template #left>
            <f-resize-pane min="200px" max="40%" initial="200px">
                <h2>Mina uppgifter</h2>
                <p>[Menypanel här]</p>
            </f-resize-pane>
        </template>
        <template #content>
            <main>
                <router-view />
            </main>
        </template>
        <template #right>
            <f-resize-pane min="200px" max="40%" initial="200px"> [Detaljpanel här] </f-resize-pane>
        </template>
    </f-page-layout>
</template>

<style scoped>
::part(grid awesome-layout) {
    grid-template:
        "header header header" min-content
        "left contextbar contextbar" min-content
        "left toolbar toolbar" min-content
        "left content right" 1fr
        / min-content 1fr;
}

::part(area header) {
    background: var(--f-background-pageheader-primary);
    color: var(--fkds-color-text-inverted);
}

::part(area contextbar) {
    background: var(--fkds-color-background-secondary);
}

::part(area toolbar) {
    background: var(--fkds-color-background-secondary);
}

::part(area left) {
    background: var(--fkds-color-background-secondary);
}

::part(area right) {
    background: var(--fkds-color-background-secondary);
}
</style>
