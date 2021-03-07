<template>

  <v-container fluid>
      <v-form>
          <v-file-input label="Selecione as Legendas" prepend-icon="mdi-message-text"
            append-icon="mdi-send" outlined multiple chips v-model="files" 
            @click:append-outer="processSubtitles"/>

      </v-form>
      <div class="pills">
          <Pill v-for="word in groupedWords" :key="word.name" :name="word.name" 
            :amount="word.amount" />
      </div>
  </v-container>

</template>

<script>
import Pill from './Pill'


export default {
    components: { Pill },
    data: function () {
        return {
            files: [],
            groupedWords: [
                { name: "i", amount: 900 },
                { name: "you", amount: 853 },
                { name: "he", amount: 1234 },
            ],
        };
    },
    methods: {
        processSubtitles() {
            console.log(this.files)
        }
    }
};
</script>

<style>
    .pills{
        display: flex;
        flex-wrap: wrap;
        justify-content: space-between;
    }  
</style>