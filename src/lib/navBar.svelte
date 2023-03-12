<script lang='ts'>
    import magnify from '$lib/assets/magnify.svg';
    import bellring from '$lib/assets/bellring.svg';
    import profile from '$lib/assets/profile.svg';
    
    let userPicture:string = profile;
    let userName = 'Default user';
    const user:boolean = false;
    
    if(user){
        userPicture = ' ';
        userName = ' ';
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
        <button><img src={bellring} alt="Bellring notification"></button>
    </div>

    <div id="userIDPIC-container">
        <div id='userPic-container'>
            <img src={userPicture} alt="User profile image">
        </div>
        <div id='userID-container'>
            <span>{userName}</span>
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

</style>