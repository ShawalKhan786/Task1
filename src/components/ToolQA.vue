<template>
  <v-container>
    <v-card class="text-center mt-4 mb-4" style="background-color: lightblue">
     <p style="font-size: 36px; font-weight: bold;"> Enter your own text or use one of these examples: </p>
      <br />
      <div class="d-flex flex-wrap justify-center">
        <v-btn @click="setFoodText" class="mr-5 mb-2">food</v-btn>
        <v-btn @click="setTechText" class="mr-5 mb-2">tech</v-btn>
        <v-btn @click="setElectronicsText" class="mr-5 mb-2">electronics</v-btn>
        <v-btn @click="clearTextarea" class="mb-2">Clear</v-btn>
      </div>
    </v-card>
   
     <v-radio-group v-model="selectedLanguage" inline class="centered-radio">
      <v-radio label="English" value="en"></v-radio>
      <v-radio label="German" value="de"></v-radio>
    </v-radio-group>
   



    <v-card >
      <v-textarea
      v-model="textareaValue"
        counter
        :label="textareaLabel"
        :rules="rules"
        
        rows="9"
      ></v-textarea>
      <v-textarea
        counter
        label="Question"
        :rules="rules"
      
        rows="2"
      ></v-textarea>
      <v-card v-if="showAnswerCard" height="100px"  style="background-color: lightblue"></v-card>
      <br>
      <v-row justify="center">
        <v-btn
          class="mb-2"
          width="800px"
          style="background-color: rgb(155, 233, 149)"
          @click="showAnswerCard = !showAnswerCard; " >Get The Answer</v-btn
        >
      </v-row>
    </v-card>
   
  </v-container>
</template>

<script>

export default {
  name: "ToolQA",
  data() {
    return {
      selectedLanguage: "en",
      textareaValue: '', // Initialize an empty value
      rules: [],
      showAnswerCard: false  
    };
  },
  computed: {
    textareaLabel() {
      const labelPrefix =
        this.selectedLanguage === "en"
          ? "Write Your Passage Here... "
          : "Schreibe deinen Text hier... ";
      const labelSuffix = `(${this.selectedLanguage === "en" ? "English" : "German"})`;

      return this.textareaValue === "" ? labelPrefix + labelSuffix : null;
    }
  },
  methods: {
    
    setFoodText() {
      this.textareaValue =
        this.selectedLanguage === "en"
          ? "Text related to food goes here. This is an example for food in English."
          : "Text für Lebensmittel geht hier hin. Dies ist ein Beispiel für Essen in German.";
    },
    setTechText() {
      this.textareaValue =
        this.selectedLanguage === "en"
          ? "Text related to technology goes here. This is an example for tech in English."
          : "Text für Technologie geht hier hin. Dies ist ein Beispiel für Technik in German.";
    },
    setElectronicsText() {
      this.textareaValue =
        this.selectedLanguage === "en"
          ? "Text related to electronics goes here. This is an example for electronics in English."
          : "Text für Elektronik geht hier hin. Dies ist ein Beispiel für Elektronik in German.";
    },
    clearTextarea() {
      this.textareaValue = "";
    },
    
  }
};
</script>
<style scoped>
.v-label.v-label--active {
  font-size: 58px; /* Adjust the font size as needed */
  font-weight: bold;
}
.centered-radio {
  display: flex;
  justify-content: center;
}
</style>
