<template>
    <section>
        <button v-if="type == 'Button'" class="btn btn-danger w-100"> {{ btn }} </button>
        <button 
            v-if="type == 'Modal'"
            type="button" 
            class="btn btn-danger w-100" 
            data-bs-toggle="modal" 
            data-bs-target="#exampleModal"
        >
            {{ btn }}
        </button>
    </section>
</template>

<script>
export default {
    props: {
        btn: String,
        type: String
    }
}
</script>