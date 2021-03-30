<template>
    <div class="container">
        <div>
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR3aY1WtUZmE4ACV-W7TUfiqrnmqotQA2vK2Q&usqp=CAU" alt="placeholder">
        </div>
        <div>
            <h2>{{event.title}}</h2>
            <p>{{event.description}}</p>
            <div class="button-section">
                <div><button>Add to favorites</button></div>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'Event',
    props: ["event"]
}
</script>

<style>

img {
    margin-right: 1rem;
}

button {
    border-radius: 10%;
    border: none;
    background-color: aquamarine;
    font-size: 1rem;

}
.container {
    display: flex;
    margin: 2rem;
    font-family: Arial, Helvetica, sans-serif;
}
</style>