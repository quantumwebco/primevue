<template>
    <DocSectionText v-bind="$attrs">
        <p>
            Filtering allows searching items in the list using an input field at the header. In order to use filtering, enable <i>filter</i> property. By default, optionLabel is used when searching and <i>filterFields</i> can be used to customize the
            fields being utilized. Furthermore, <i>filterMatchMode</i> is available to define the search algorithm. Valid values are "contains" (default), "startsWith" and "endsWith".
        </p>
    </DocSectionText>
    <div class="card flex justify-center">
        <MultiSelect v-model="selectedCities" :options="cities" filter optionLabel="name" placeholder="Select Cities" :maxSelectedLabels="3" class="w-full md:w-80" />
    </div>
    <DocSectionCode :code="code" />
</template>

<script setup lang="ts">
import MultiSelect from '@/volt/MultiSelect.vue';
import { ref } from 'vue';

const selectedCities = ref(null);
const cities = ref([
    { name: 'New York', code: 'NY' },
    { name: 'Rome', code: 'RM' },
    { name: 'London', code: 'LDN' },
    { name: 'Istanbul', code: 'IST' },
    { name: 'Paris', code: 'PRS' }
]);

const code = ref(`
<template>
    <div class="card flex justify-center">
        <MultiSelect v-model="selectedCities" :options="cities" filter optionLabel="name" placeholder="Select Cities" :maxSelectedLabels="3" class="w-full md:w-80" />
    </div>
</template>

<script setup lang="ts">
import MultiSelect from '@/volt/MultiSelect.vue';
import { ref } from 'vue';

const selectedCities = ref(null);
const cities = ref([
    { name: 'New York', code: 'NY' },
    { name: 'Rome', code: 'RM' },
    { name: 'London', code: 'LDN' },
    { name: 'Istanbul', code: 'IST' },
    { name: 'Paris', code: 'PRS' }
]);
<\/script>
`);
</script>
