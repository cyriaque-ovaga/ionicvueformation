<template>
  <base-layout page-title="All memories">
    <ion-list>
      <ion-item
        v-for="item in memories"
        :key="item.id"
        @click="() => router.push('/memories/' + item.id)"
      >
        <ion-thumbnail slot="start">
          <ion-img :src="item.image" :alt="item.title"></ion-img>
        </ion-thumbnail>
        <ion-label>
          {{ item.title }}
        </ion-label>
      </ion-item>
    </ion-list>
  </base-layout>
</template>

<script lang="ts">
import { IonList, IonItem, IonImg, IonThumbnail, IonLabel } from "@ionic/vue";
import { defineComponent } from "vue";
import { useRouter } from "vue-router";
export default defineComponent({
  components: {
    IonList,
    IonItem,
    IonImg,
    IonThumbnail,
    IonLabel,
  },
  setup() {
    const router = useRouter();
    return { router };
  },
  data() {
    return {
      memories: [
        {
          id: "m1",
          image:
            "https://imagesvc.meredithcorp.io/v3/mm/image?url=https%3A%2F%2Fstatic.onecms.io%2Fwp-content%2Fuploads%2Fsites%2F28%2F2020%2F07%2F21%2Fcascade-mountains-range-USMNTNS0720.jpg",
          title: "A trip to a mountains",
          description: "A really nice trip",
        },
        {
          id: "m2",
          image:
            "https://q-xx.bstatic.com/xdata/images/hotel/840x460/124820044.jpg?k=a7bbf4a00556835a8505f92225dcf3dfeb9d0ae9ba96ab15c4f8733dcdec426c&o=",
          title: "Surfing the sea side",
          description: "A really nice sea side",
        },
        {
          id: "m3",
          image:
            "https://i1.wp.com/www.additudemag.com/wp-content/uploads/2020/07/The-5-Challenges-and-Solutions-for-Eating-Smart_1920x1080.jpg?resize=1280%2C720px&ssl=1",
          title: "Good eating",
          description: "A really good food",
        },
      ],
    };
  },
});
</script>
