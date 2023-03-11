<script lang='ts'>
    import magnify from '$lib/assets/magnify.svg';
</script>
<nav>
    <div id='search-container'>
        <form action="">
            <button><img src={magnify} alt="Magnify img" srcset=""></button>
            <input type="text" name='search' placeholder="Type something...">
        </form>
    </div>
    <div id='notiUser'>

    </div>
    <div id='btns'>
        <button type="button">
            NEW
        </button>
        <button type="button">
            UPLOAD
        </button>
        <button type="button">
            SHARE
        </button>
    </div>
</nav>


<style lang='scss'>
    div#search-container{
        button{
            width: 30px;
            border: 0;
            border-radius: 10px;
        }
    }
</style>