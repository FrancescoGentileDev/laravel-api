<template>
    <article>
        <div class="card" style="width: 20rem">
            <img v-if="details.image" class="card-img-top" :src="details.image" alt="Card image cap" />
            <div class="card-body">
                <p class="card-subtitle text-muted">{{ date }}</p>
                <h5 class="card-title">{{ details.title }}</h5>
                <p class="card-text">
                    Some quick example text to build on the card title and make
                    up the bulk of the card's content.
                </p>
            </div>
            <div class="card-footer text-muted">
            {{ details.category.name }}
            </div>
        </div>
    </article>
</template>

<script>
export default {
    props: {
        details: Object
    },
    data() {
        return {
            date: undefined,
        }
    },
    created() {
      let string = this.details.updated_at;
      let date = new Date(string).toLocaleString('it-IT')
      this.date = date;

    },
};
</script>

<style lang="scss" scoped>
</style>
