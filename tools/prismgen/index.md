<style>
.tool {
    padding: 35px;
    border-radius: 5px;
    width: 100%;
    display: block;
    margin-top: 2.5em;
    display: flex;
    justify-content: space-around;
    background: var(--main_dark);
    align-items: center;
    text-decoration: none
}
.tool__image {
    height: 120px
}
.tool__heading,
.tool__description {
    margin: 0
}
.tool__description {
    font-weight: 400;
    width: 80%;
    margin-top: 1.25em;
    color: var(--main_lightgrey);
}
.tool__heading {
    color: #fff
}
</style>
<a class="tool" href="//prismgen.kottsov.com">
    <div>
        <h3 class="tool__heading">PrismJS Generator</h3>
        <h5 class="tool__description">Online tool to convert the unhighlighted code to a static highlighted HTML markup using PrismJS. Now the user’s browser doesn’t have to highlight it during every page load.</h5>
    </div>
    {{< image src="thumbnail.png" class="tool__image" >}}
</a>