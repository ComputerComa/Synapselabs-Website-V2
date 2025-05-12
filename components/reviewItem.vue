<template>
    <div class="review-container">
       
    <div class="review-item">
        <div class="review-header">
            <picture>
                <img :src="GetImageSrc" :alt="GetImageAlt" class="author-image" />
                
            </picture>
            <div class="review-info">
                <h3 class="author-name">{{ author }}</h3>
                <p class="submission-date">{{ formattedDate }}</p>
            </div>
        </div>
        <div class="review-body">
            <p class="service-provided"><strong>Service Provided:</strong> {{ serviceProvided }}</p>
            <p class="review-text">{{ reviewText }}</p>
        </div>
        <div class="review-footer">
            <p class="rating"><strong>Overall Rating:</strong> {{ rating }} / 5</p>
        </div>
    </div>
    </div>
</template>

<script>
export default {
    name: "ReviewItem",
    props: {
        author: {
            type: String,
            required: true,
        },
        rating: {
            type: String,
            required: true,
            validator: (value) => parseInt(value) >= 0 && value <= 5,
        },
        reviewText: {
            type: String,
            required: true,
        },
        serviceProvided: {
            type: String,
            required: true,
        },
        submissionDateTime: {
            type: String,
            required: true,
            
        }
    },
    computed: {
        formattedDate() {

            const dateTime = new Date(this.submissionDateTime || Date.now());

            return dateTime.toLocaleString("en-US", {
                year: "numeric",
                month: "long",
                day: "numeric",
                hour: "2-digit",
                minute: "2-digit",
            });
        },
        GetImageSrc() {
            return `/img/Stars/${this.rating}.png`;
        },
        GetImageAlt() {
            return `Image with ${this.rating} stars`;
        },
    },
};
</script>

<style scoped>
.review-container {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    margin-top: 20px;
}
.review-item {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 16px 16px 16px 16px;
    margin-left: 16px;
    margin-right: 16px;
    margin-bottom: 5px;
    margin-top: 5px;
    width: 75%;
    background-color: #fff;
    box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.review-header {
    display: flex;
    align-items: center;
    margin-bottom: 12px;
}

.author-image {

    height: 50px;
    object-fit: fill;
    margin-right: 12px;
}

.review-info {
    display: flex;
    flex-direction: column;
}

.author-name {
    font-size: 1.2em;
    margin: 0;
}

.submission-date {
    font-size: 0.9em;
    color: #666;
}

.review-body {
    margin-bottom: 12px;
}

.service-provided {
    font-size: 1em;
    margin: 0 0 8px;
}

.review-text {
    font-size: 1em;
    color: #333;
}

.review-footer {
    font-size: 1em;
    font-weight: bold;
    color: #444;
}
</style>