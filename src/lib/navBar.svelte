<script lang='ts'>
    import magnify from '$lib/assets/magnify.svg';
    import bellring from '$lib/assets/bellring.svg';
    import profile from '$lib/assets/profile.svg';
	import { PROCESSOR_IDENTIFIER } from '$env/static/private';
    
    let userPicture:string = profile;
    let userName = 'Default user';
    const user:boolean = false;
    
    if(user){
        userPicture = ' ';
        userName = ' ';
    }

    let button:any;

    let open:boolean = false;
    let top:number = 0;
    let left:number = 0;

    $:if(open){
        setDropdownPosition();
    }

    function setDropdownPosition() {
        const rect = button.getBoundingClientRect()();
        top = rect.bottom;
        left = rect.left;
    }

</script>
<nav>
    <div id='search-container'>
        <form action="">
            <button><img src={magnify} alt="Magnify img" srcset=""></button>
            <input type="text" name='search' placeholder="Type something...">
        </form>
    </div>

    <div id='notification-container'>
        <button bind:this={button} on:click={() => open = !open}><img src={bellring} alt="Bellring notification"></button>
    </div>


    <div id="userIDPIC-container">
        <div id='userPic-container'>
            <img src={userPicture} alt="User profile image">
        </div>
        <div id='userID-container' class="dropdown">
            <span>{userName}</span>
            <div class='dropdown-content'>
                <a href="#">Log out</a>
            </div>
        </div>
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

{#if open}
    <ul class="notiContent" style:top={top} style:left={left}>
        <li>Notification 1</li>
        <li>Notification 1</li>
        <li>Notification 1</li>
    </ul>
{/if}


<style lang='scss'>

    %smallBtn{
        width: 33px;
        border: 0;
        border-radius: 10px;
    }

    nav{
        position: sticky;
        top: 0px;
        width: 100dvw;
        display: grid;
        grid-template-columns: repeat(3, auto);
        grid-template-rows: 1fr 1fr;
    }

    div#search-container{
        button{
            @extend %smallBtn;
        }

        margin-top: auto;
        margin-bottom: auto;

        form{        
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 1rem;
        }
   
        input[type='text']{
            padding-left: 14px;
            width: 50dvw;
            height: 4dvh;
            border: 0;
            border-radius: 10px;
            background-color: aqua
        }
    }

    div#notification-container{
        button{
            @extend %smallBtn;
        }
    }

    .notiContent{
        position: absolute;
        display: grid;
        gap: 0.25rem;
        margin: 0.5rem 0 0 0.5rem;
        padding: 0;
    }

    ul li {
		padding: 0;
		text-indent: 0;
		list-style-type: none;
	}

    div#userPic-container{
        width: 45px;
        margin-top: 2px;
    }

    #notification-container{
        display: flex;
        justify-content: end;
        align-items: center;
    }

    div#userIDPIC-container{
        display: flex;
        justify-content: start;
        align-items: center;
        gap: 10px;
        margin-left: 1rem;
    }

    div#btns{
        grid-column: 1 / 4;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: 10%;       

        button{
            width: 80px;
            height: 30px;
        }

    }

    .dropdown{
        position: relative;
        display: inline-block;

        &:hover .dropdown-content{
            display: block;
        }
    }

    .dropdown-content{ 
        display: none;
        position: absolute;
        min-width: 160px;
        z-index: 1;
    
        a{
            display: block;
            text-decoration: none;
        }
    }

</style>