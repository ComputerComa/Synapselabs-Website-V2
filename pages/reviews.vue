<template>
    <section>

        <div class="container">
            <h1>Reviews</h1>
            <p>Here are some reviews from our customers:</p>
        </div>
    </section>  
        <section>
            <NuxtLoadingIndicator />
      
        <review-item v-if="success"
          v-for="(review, index) in reviews"
        :key="index"
          :author="review.Author"
          :serviceProvided="review.ServiceProvided"
          :submissionDateTime="review.SubmissionDateTime"
          :rating="review.Rating"
          :reviewText="review.Review"
        ></review-item>
        <div class="review-item" v-if="success === false">
            <p>No reviews available.</p>
        </div>
    </section>
    </template>

    <script>
    import { useFetch } from '@vueuse/core';

    export default {
        data() {
            return {
                reviews: [],
                success: false,
            };
        },
        async created() {
            try {
                const { data, error } = await useFetch("https://n8n.synapselabs.xyz/webhook/reviews").json();
                if (error.value) {
                    throw new Error(`Fetch error: ${error.value.message}`);
                }
                console.log("Fetched reviews:", data.value);
                this.reviews = data.value.reviews;
                this.success = data.value.success;
                console.log("Fetched reviews:", data.value.reviews);
                console.log("Fetched success:", data.value.success);
                
            } catch (error) {
                console.error("Error fetching reviews:", error);
            }
        },
    };


</script>
<script setup>
useHead({

  title: 'Reviews | Synapselabs.xyz',
  meta: [
    {
      name: 'description',
      content: 'Your local, trusted partner for professional tech consulting and support. We specialize in a wide range of services including computer repairs, printer setup and repairs, as well as comprehensive network planning and installation.',
    },
  ],
})
</script>