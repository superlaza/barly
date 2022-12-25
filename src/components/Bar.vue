<script setup>
    import StarRating from 'vue-star-rating';
    
    const props = defineProps({
        // name: String,
        bar: Object,
    });
</script>

<template>
  <div class="bar">
    <img class="bar-image" referrerpolicy="no-referrer" :src="bar.img" />
    <div class="bar-details">
        <h3 class="bar-name">{{bar.name}}</h3>
        <div class="rating">
            <span class="bar-rating">
                {{ bar.rating[0] }}
            </span>
            <star-rating 
                :read-only="true"
                :round-start-rating="false"
                :rating="bar.rating[0]"
                :star-size="15"
                :show-rating="false"
            />
            <span class="bar-rating">
                ({{ bar.rating[1] }})
            </span>
        </div>
        <a :href="'https://maps.google.com?saddr=Current+Location&daddr='+bar.name" target="_blank">{{bar.address}}</a>
        <!-- <span>{{bar.current_density}}</span> -->
    </div>
  </div>
</template>

<style scoped>
h3 {
    font-weight: bolder;
}
.bar {
  display: flex;
  width: 100%;
  height: 200px;
  border: 1px solid #ccc;
  border-radius: 4px;
  overflow: hidden;
  margin: 0 auto;

  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.5);
  padding: 20px;
  background-color: #333;

  transition: all 1s ease-in-out;
}

.bar-image {
  /* width: 50%;
  height: 100%; */
  object-fit: cover;
  padding: 10px;
}

.bar-content {
  width: 50%;
  padding: 16px;
}

.bar-name {
  margin: 15px 0 25px 0;
  color: whitesmoke;
}

.bar-rating {
  margin: 8px 0;
  font-size: 14px;
  color: #888;
  display: inline;
}

.bar-description {
  margin: 0;
  font-size: 14px;
  line-height: 1.5;
  color: #666;
}

.vue-star-rating {
    padding: 0 5px;
    top: 2px;
    display: inline-flex;
}
</style>
