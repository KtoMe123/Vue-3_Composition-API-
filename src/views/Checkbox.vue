<script setup>
import {ref} from 'vue'
import Checkbox from '@/components/Checkbox/Checkbox.vue'
import CheckboxGroup from '@/components/Checkbox/CheckboxGroup.vue'

const checkboxActive = ref(true)
const checkboxDisabled = ref(true)
const checkboxDisabledChecked = ref(true)

const listOfCompany = ref([
    {name: "Microsoft", id:'h1'},
    {name: "Apple", id:'h2'},
    {name: "Valve", id:'h3'},
    {name: "Z-Labs", id:'h4'},
])

const selectedCompany = ref(['h1', 'h3'])
const switchProfessional = ref(false);
</script>


<template>
    <h1 class="heading-1">Checkbox</h1>
    <h2 class="heading-2">Checkbox Active</h2>
    <div class="line">
        <checkbox 
            label="Checkbox Active"
            id="checkboxActive"
            name="checkboxActive"
            value="nice"
            v-model:checked="checkboxActive"
        />
    </div>
    <h2 class="heading-2">Checkbox Disabled</h2>
    <div class="line">
        <checkbox 
            label="Checkbox Disabled"
            id="checkboxDisabled"
            name="checkboxDisabled"
            value="nice"
            :disabled="checkboxDisabled"
            v-model:checked="checkboxDisabledChecked"
        />
    </div>
    <h2 class="heading-2">Checkbox Group</h2>
    <div class="line line_block">
        <p>Selected Company: {{selectedCompany}}</p>
        <checkbox-group 
            v-model:value="selectedCompany"
            name="company"
            :options="listOfCompany"
        />
    </div>
    <h2 class="heading-2">Switch</h2>
    <div class="line line_block">
        <p>Switch: {{switchProfessional}}</p>
        <checkbox 
            label="I'm a professional"
            id="switch"
            name="switch"
            value="I'm a professional"
            type="switch"
            v-model:checked="switchProfessional"
        />
    </div>
</template>