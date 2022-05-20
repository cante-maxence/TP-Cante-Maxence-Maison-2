<template>
        <figure class="m-5 bg-gray-50 grid grid-flow-row-dense grid-cols-3 ">
            <img class="w-full h-48 object-cover col-span-3" :src="image" alt="" />

            <figcaption class="relative p-5 pt-8 border-2 border-t-0 rounded-lg border-indigo-100 contents">

                <section class="contents">
                    <div class="contents">
                        <div class="text-xl font-bold text-left text-indigo-500 col-span-1">${{ price }} </div>
                        <div class="rounded-full mt-2">
                            <heart :class="{ 'fill-red-400': favori }" />
                        </div>
                    </div>
                    <div class="text-gray-500 text-base inline-block col-span-3">/month</div>
                    <h3 class="text-xl text-gray-900 col-span-3">{{ location }}</h3>
                    <div class="text-gray-500 col-span-3">{{ adress }}</div>
                    <hr class="m-4 border-indigo-100" />
                    <div class="justify-between text-sm contents">
                        <div class="w-max"><bed class="h-5 w-5 mr-1 inline-block col-span-1"/>{{nbrbed}} Beds</div>
                        <div class="w-max"><bath class="h-5 w-5 mr-1 inline-block col-span-1"/>{{nbrbath}} Bath</div>
                        <div class="w-max"><dimensions class="h-5 w-5 mr-1 inline-block col-span-1"/>{{ size }}</div>
                    </div>
                </section>
            </figcaption>
        </figure>
</template>

<script>
import dimensions from "./icones/dimensions.vue";
import bed from "./icones/beds.vue";
import bath from "./icones/bath.vue";
import heart from "./icones/heart.vue";

export default {
  props: {
    location: String,
    adress: String,
    price: Number,
    favori: Boolean,
    image: String,
    nbrbath: Number,
    nbrbed: Number,
    size: String
  },
  components: { bath, heart, bed, dimensions },
};
</script>