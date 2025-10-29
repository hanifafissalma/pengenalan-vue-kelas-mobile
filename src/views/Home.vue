<template>
    <div class="main-content">
        <div class="fluid-container">
            <TheWelcome />
        </div>
        <div class="fluid-container">
            <div class="section-services" id="services">
                <div class="table-wrapper">
                    <table class="fl-table">
                        <thead>
                            <tr>
                                <th>Nama</th>
                                <th>NIM</th>
                                <th>Aksi</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr v-for="(mhs, index) in students" :key="index">
                                <td>{{ mhs.nama }}</td>
                                <td>{{ mhs.nim }}</td>
                                <td>
                                    <button class="btn-detail" @click="goToDetail(mhs.nim)">
                                        Detail
                                    </button>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
    import TheWelcome from '@/components/TheWelcome.vue'
    import { useRouter } from 'vue-router'

    const router = useRouter()

    interface StudentData {
        nama: string
        nim: string
    }
    const OneStudent: StudentData =  {
            "nama": "TEDI FAUZI",
            "nim": "043343035"
        }

    const students: StudentData[] = [
        {
            "nama": "TEDI FAUZI",
            "nim": "043343035"
        },
        {
            "nama": "MUTIARA DIVA ALINDA",
            "nim": "048721035"
        },
        {
            "nama": "ARROCHMAN ARDIANSAH",
            "nim": "049509394"
        },
        {
            "nama": "JUONE RIZKI HERIYANTO SAMOSIR",
            "nim": "049540646"
        },
        {
            "nama": "MUHAMAD WAHYU KADENGKANG",
            "nim": "049627753"
        }
    ]

    const goToDetail = (nim: string): void => {
        router.push({ name: 'detail', params: { nim } })
    }
</script>