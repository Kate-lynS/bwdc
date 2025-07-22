<script>
    import Scroller from "../lib/Scroller.svelte";
    import ObservedArticleText from "../lib/ObservedArticleText.svelte";

    // this `options` object below is passed into the <ObservedArticleText>
    // component, and from there it gets passed to the IntersectionObserver object w
    // when it's created.
    // the thresholds to fire the callback are 85% and 95%. in the callback function,
    // we check whether the visible area is >= 90%. so, triggering the callback at
    // 85% and 95% ensures we trigger the correct change in background color
    // whether the element is being scrolled into the viewport or out of the viewport.
    const options = {
        threshold: [0.85, 0.95],
    };

    const callback = (entries, observer) => {
        entries.forEach((entry) => {
            const elem = entry.target;

            if (entry.intersectionRatio >= 0.9) {
                // "active" state
                elem.style.backgroundColor = "#e3ff00";
            } else if (entry.intersectionRatio < 0.9) {
                // "inactive" state
                elem.style.backgroundColor = "#888888";
            }
        });
    };
</script>

<Scroller layout="left">
    <div slot="sticky">
        <p>
            While the scatterplot highlights a noticeable correlation between higher education levels and increased rates of health insurance among women of color, it's important to explore the why.
            <br> Data rarely tells the full story on its own—many social, economic, and
            structural factors shape these outcomes.
        </p>
    </div>

    <div slot="scrolly">
        <ObservedArticleText {callback} {options}>
            <p>Factor 1: Employment-based insurance access</p>
        </ObservedArticleText>

        <ObservedArticleText {callback} {options}>
            <p>Factor 2: Income levels and affordability of private plans</p>
        </ObservedArticleText>

        <ObservedArticleText {callback} {options}>
            <p>Factor 3: Awareness and literacy about insurance options</p>
        </ObservedArticleText>
    </div>
</Scroller>
