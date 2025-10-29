<template>
    <div class="main-container">
        <div class="fluid-container">
            <br/><br/><br/><br/>
            <div class="section-contact">
                <fieldset>
                    <label>Bilangan 1:</label>
                    <input type="number" v-model.number="bilangan1" />
                </fieldset>
                <fieldset>
                    <label>Bilangan 2:</label>
                    <input type="number" v-model.number="bilangan2" />
                </fieldset>

                <fieldset>
                    <p>Hasil: {{ hasil }}</p>
                </fieldset>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
    import { ref, computed } from 'vue'

    const bilangan1 = ref<number>(0)
    const bilangan2 = ref<number>(0)

    const hasil = computed(() => bilangan1.value * bilangan2.value)
</script>
