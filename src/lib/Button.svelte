<script>
    export let text
    export let onClick
    export let backgroundColor
    export let fontSize
    export let disabled
</script>

<button disabled ={disabled} on:click={onClick} style="background-color: {backgroundColor}; font-size: {fontSize}px" class="learn-more">{text}</button>

<style>
    
    @import url('https://fonts.googleapis.com/css?family=Rubik:700&display=swap');
    /* $bg: #fff;
    $text: #382b22;
    $light-pink: #fff0f0;
    $pink: #ffe9e9;
    $dark-pink: #f9c4d2;
    $pink-border: #b18597;
    $pink-shadow: #ffe3e2; */
    /* button {
        color: white;
        padding: 10px 20px;
        border: none;
        border-radius: 5px;
        cursor: pointer;
        font-size: 16px;
        font-weight: bold;
    } */
    button {
        position: relative;
        display: inline-block;
        cursor: pointer;
        outline: none;
        border: 0;
        vertical-align: middle;
        text-decoration: none;
        font-family: 'Rubik', sans-serif;
        &.learn-more {
            font-weight: 600;
            color: '#fff';
            text-transform: uppercase;
            padding: 1.25em 2em;
            background: light-pink;
            border: 2px solid #b18597;
            border-radius: 0.75em;
            transform-style: preserve-3d;
            transition: transform 150ms cubic-bezier(0, 0, 0.58, 1), background 150ms cubic-bezier(0, 0, 0.58, 1);
            &::before {
            position: absolute;
            content: '';
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: #f9c4d2;
            border-radius: inherit;
            box-shadow: 0 0 0 2px #b18597, 0 0.625em 0 0 #ffe3e2;
            transform: translate3d(0, 0.75em, -1em);
            transition: transform 150ms cubic-bezier(0, 0, 0.58, 1), box-shadow 150ms cubic-bezier(0, 0, 0.58, 1);
            }
            &:hover {
            background: #ffe9e9;
            transform: translate(0, 0.25em);
            &::before {
                box-shadow: 0 0 0 2px #b18597, 0 0.5em 0 0 #ffe3e2;
                transform: translate3d(0, 0.5em, -1em);
            }
            }
            &:active {
            background: #ffe9e9;
            transform: translate(0em, 0.75em);
            &::before {
                box-shadow: 0 0 0 2px #b18597, 0 0 #ffe3e2;
                transform: translate3d(0, 0, -1em);
            }
            }
        }
        }
</style>