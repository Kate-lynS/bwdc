<script>
    import Scroller from "../lib/Scroller.svelte";
    import ArticleText from "../lib/ArticleText.svelte";
</script>

<div>
    <Scroller layout="right">
        <img class="flower-img" src="flower.png" alt="figure with flowers!" />
    </Scroller>
</div>

<style>
    .flower-img {
        width: 25%;
        margin: 0px auto;
    }
</style>
