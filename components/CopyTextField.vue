<template>
    <div>
        <v-row>
            <v-col cols="7" offset="2">
                <v-text-field placeholder="... Nhập text ở đây" filled outlined clearable v-model="text"
                    base-color="primary"></v-text-field>
            </v-col>
            <v-col cols="1">
                <v-btn dark x-large color="primary" @click="copyText" width="100%"> COPY </v-btn>
            </v-col>
        </v-row>


        <v-snackbar v-model="snackbar" :timeout="timeout" color="success" right top icon="success">
            Copied
            <v-icon color="white" right small>
                mdi-checkbox-marked-circle
            </v-icon>
        </v-snackbar>

    </div>
</template> 

<script>
import { Clipboard } from '@capacitor/clipboard';

export default {
    data() {
        return {
            text: "",
            snackbar: false,
            timeout: 1000,
        }
    },
    methods: {
        copyText: async function () {
            this.snackbar = true;
            await Clipboard.write({
                string: this.text,
            });
        }
    }
}
</script>