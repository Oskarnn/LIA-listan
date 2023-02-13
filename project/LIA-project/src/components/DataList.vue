<script>
    export default {
        created() {
            this.fetch();
        },

        data() {
            return {
                listClass: "list-class",
                companies: null,

            };
        },

        methods: {
            fetch(){
                fetch('/info.json')
                .then((response) => response.json())
                .then((result) =>  {
                    this.companies = result})

            },
        //  delete() LÄGGA IN FUNKTION FÖR ATT VISA TT LISTAN UPPDATERATS FRÅN 
        }
    }
</script>

<template>
    <section :class="listClass">
        <div class="list" id="list-1">
            <h3>Inväntar svar</h3>
            <ul v-for="company in companies">
                <li v-if="company.status === 'Inväntar svar'">
                    <p>{{ company.name }}</p>
                    <p>{{ company.info }}</p>
                    <p>{{ company.location }}</p>
                </li>
            </ul>
        </div>
        <div class="list" id="list-2">
            <h3>Tackat nej</h3>
            <ul v-for="company in companies">
                <li v-if="company.status === 'Tackat nej'"><p>{{ company.name }}</p>
                    <p>{{ company.info }}</p>
                    <p>{{ company.location }}</p>
                </li>
            </ul>
        </div>
        <div class="list" id="list-3">
            <h3>Kallad på intervju</h3>
            <ul v-for="company in companies">
                <li v-if="company.status === 'Kallad på intervju'"><p>{{ company.name }}</p>
                    <p>{{ company.info }}</p>
                    <p>{{ company.location }}</p></li>
            </ul>
        </div>
    </section>
    <button @click="fetch()">Uppdatera listan</button>
</template>

<style scoped>
    .list-class {
        font-family: Roboto;
        display: flex;
        justify-content: space-evenly;
        align-items: flex-start;
        margin-top: 5vh;

    }

    .list {
        min-width: 300px;

    }

    #list-1{
        background-color: rgba(255,255,0, 0.3);

    }
    #list-2{
        background-color: rgba(239, 90, 90, 0.233);
    }
    #list-3{
        background-color: rgba(118, 211, 136, 0.233);
    }
</style>
