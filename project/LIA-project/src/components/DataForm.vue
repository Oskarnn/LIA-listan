<script>
export default {
    data(){
        return {
            check: null,
            formData: {
                id:null,
                name: null,
                info: null,
                location: null,
                status: null },
            showWarn: false,

        }

    },
    watch: {
        check(checkWas, checkIs) {
            console.log(checkIs, checkWas )
        }
    }
}

</script>

<template>
     <div>
    <h3>Här kan jag lägga till och ändra företagen i listan</h3>
    <p>Vad vill jag göra?</p>
  </div>
    <form id="action">
        <label>Lägg till?</label>
        <input type="radio" v-model="check" value="POST">
        <label>Ändra?</label>
        <input type="radio" v-model="check" value="PUT">
        <label>Ta bort?</label>
        <input type="radio" v-model="check" value="DELETE">
    </form>
    <form v-if="check === 'POST'" class="post-form">
        <label>Företagets namn</label>
        <input type="text" v-model="formData.name">
        <label>Företagets namn</label>
        <input type="text" v-model="formData.info">
        <label>Företagets namn</label>
        <input type="text" v-model="formData.location">
        <label>Inväntar svar</label>
        <input type="radio" v-model="formData.status" value="Inväntar svar">
        <label>Tackat nej</label>
        <input type="radio" v-model="formData.status" value="Tackat nej">
        <label>Kallad på intervju</label>
        <input type="radio" v-model="formData.status" value="Kallad på intervju">

        <input :disabled="formData.namn || formData.status == null" type="submit" value="Lägg till">

    </form>

    <form class="put-form" v-else-if="check === 'PUT'">
        <input type="submit" value="Ändra">
    </form>


    <div class="delete-form" v-else>


        <input v-if="showWarn === false" type="button" value="Ta bort" @click="showWarn = true">
    </div>
    <div v-if="showWarn"><p>Är du säker att du vill radera?


    <input  type="button" value="Avbryt" @click="showWarn = false">
    </p></div>


</template>

<style scoped>

</style>
