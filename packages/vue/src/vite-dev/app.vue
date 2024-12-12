<template>
    <div>
        <f-wizard v-model="current" header-tag="h2" @completed="onCompleted">
            <f-wizard-step key="foo" :use-error-list="false" title="Stegrubrik 1">
                <f-datepicker-field v-model="date" v-validation.required> Etikett-rubrik </f-datepicker-field>
                <f-text-field v-validation.maxLength="{ maxLength: { length: 100 } }">
                    Etikett-rubrik (frivillig)
                </f-text-field>
            </f-wizard-step>

            <f-wizard-step key="bar" :use-error-list="false" title="Stegrubrik 2">
                <f-datepicker-field v-model="date" v-validation.required> Etikett-rubrik </f-datepicker-field>
                <f-text-field v-validation.maxLength="{ maxLength: { length: 100 } }">
                    Etikett-rubrik (frivillig)
                </f-text-field>
            </f-wizard-step>
            <f-wizard-step key="baz" :use-error-list="false" title="Stegrubrik 3">
                <f-datepicker-field v-model="date" v-validation.required> Etikett-rubrik </f-datepicker-field>
                <f-text-field v-validation.maxLength="{ maxLength: { length: 100 } }">
                    Etikett-rubrik (frivillig)
                </f-text-field>
                <template #next-button-text> Klar </template>
            </f-wizard-step>
            <f-wizard-step key="bo" :use-error-list="false" title="Stegrubrik 4">
                <f-datepicker-field v-model="date" v-validation.required> Etikett-rubrik </f-datepicker-field>
                <f-text-field v-validation.maxLength="{ maxLength: { length: 100 } }">
                    Etikett-rubrik (frivillig)
                </f-text-field>
                <template #next-button-text> Klar </template>
            </f-wizard-step>
        </f-wizard>
        <p v-if="done">Allt är ifyllt</p>
    </div>
</template>

<script>
import { defineComponent } from "vue";
import { FWizard, FWizardStep, FTextField, FDatepickerField } from "../components";

export default defineComponent({
    name: "WizardExampleDefault",
    components: { FWizard, FWizardStep, FTextField, FDatepickerField },
    data() {
        return {
            current: null,
            visible: true,
            done: false,
            date: "",
            options: "",
        };
    },
    methods: {
        onCompleted() {
            this.done = true;
        },
    },
});
</script>
