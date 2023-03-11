<script lang='ts'>
    import magnify from '$lib/assets/magnify.svg';
    import bellring from '$lib/assets/bellring.svg';
</script>
<nav>
    <div id='search-container'>
        <form action="">
            <button><img src={magnify} alt="Magnify img" srcset=""></button>
            <input type="text" name='search' placeholder="Type something...">
        </form>
    </div>
    <div id='notification-container'>
        <button><img src={bellring} alt="Bellring notification"></button>
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

    div#notification-container{
        button{
            width: 30px;
            border: 0;
            border-radius: 10px;
        }
    }
</style>