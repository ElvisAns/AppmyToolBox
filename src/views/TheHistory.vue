<template>
  <ion-page ref="page">
    <ion-header>
      <ion-toolbar>
        <ion-title>{{title}}</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content class="ion-padding">
      <ion-button id="open-modal" expand="block">Open</ion-button>

      <ion-modal ref="modal" trigger="open-modal" :can-dismiss="canDismiss" :presenting-element="presentingElement">
        <ion-header>
          <ion-toolbar>
            <ion-title>Modal</ion-title>
            <ion-buttons slot="end">
              <ion-button @click="dismiss()">Close</ion-button>
            </ion-buttons>
          </ion-toolbar>
        </ion-header>
        <ion-content>
          <ion-item>      
                <ion-list>
                    <ion-item v-for="(item,index) in Thedatas" :key="index">
                        <ion-label>{{item[0]}}</ion-label>
                        <ion-label>{{item[1]}}</ion-label>
                    </ion-item>
                </ion-list>
          </ion-item>
        </ion-content>
      </ion-modal>
    </ion-content>
  </ion-page>
</template>

<script>
  import {
    CheckboxCustomEvent,
    IonButtons,
    IonButton,
    IonModal,
    IonHeader,
    IonContent,
    IonToolbar,
    IonTitle,
    IonItem,
    IonLabel,
    IonPage,
  } from '@ionic/vue';
  import { defineComponent } from 'vue';

  export default defineComponent({
    name: "TheHistory",
    components: {
      IonButtons,
      IonButton,
      IonModal,
      IonHeader,
      IonContent,
      IonToolbar,
      IonTitle,
      IonItem,
      IonLabel,
      IonPage,
    },
    propos:{
        title:String,
        Thedatas:Array
    },
    data() {
      return {
        canDismiss: true,
        presentingElement: undefined,
      };
    },
    methods: {
      dismiss() {
        this.$refs.modal.$el.dismiss();
      },
      onTermsChanged() {
        this.canDismiss = CheckboxCustomEvent.detail.checked;
      },
    },
    mounted() {
      this.presentingElement = this.$refs.page.$el;
    },
  });
</script>