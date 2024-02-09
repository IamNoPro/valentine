<script>
  import svelteLogo from './assets/svelte.svg'
  import image1 from '/img1.gif'
  import image2 from '/img2.gif'
  import image3 from '/img4.gif'
  import image4 from '/img3.gif'
  import image5 from '/img5.gif'
  import image6 from '/img6.gif'
  import image7 from '/img7.gif'
  import image8 from '/img8.gif'
  import image9 from '/img9.gif'
  import image10 from '/img10.gif'
  import image11 from '/img11.gif'
  

  import Counter from './lib/Counter.svelte'
  import Button from './lib/Button.svelte'
 

  const images = [image1, image2, image3, image4, image5, image6,image7,image8,image9,image10, image11]
  const labels = ['No', 'Are you sure?', 'Really sure?', 'Are you positive???', 'if you say no, I will be sad', 'I will be very very sad', 'I will be very very very sad', 'Ok fine, I will stop asking...', 'Just kidding, PLEASE SAY YES', 'PLEASEEEEEEEEE']
  let currentImageIndex = 0;
  let labelIndex = 0
  let isDisabledNo = false
  let isDisabledYes = false

  // Define the initial button size and percentage change
  const initialButtonSize = 16; // Initial font size in pixels
  const percentageChange = 10; // Percentage change on click

  let buttons = {
    yes: {
      label: "Yes",
      size: initialButtonSize // Default size for Yes button
    },
    no: {
      label: "No",
      size: initialButtonSize // Default size for No button
    }
  };

  function handleNoClick() {
    if(labelIndex == 9){
      isDisabledYes = true
    }
    currentImageIndex = (currentImageIndex + 1) % images.length;
    labelIndex = (labelIndex + 1) % labels.length
    // buttons.no.size -= (buttons.no.size * (percentageChange / 100)); // Decrease size
    buttons.no.label = labels[labelIndex]
    buttons.yes.size += (buttons.yes.size * (percentageChange / 100)); // Increase size of Yes button
    buttons = {...buttons}
    console.log(typeof buttons.no.size.toString())
  }
  function handleYesClick() {
    currentImageIndex = (currentImageIndex + 10) % images.length
    isDisabledNo = true
  }
</script>

<div>
  <div class="picture">
    <img src={images[currentImageIndex]} class="logo" alt="Vite Logo" style="width: 200px; height: auto;" />
  </div>
  <h2>Will you be my Valentine?</h2>

  <div class="card">

    <Button text={buttons.yes.label} onClick={handleYesClick} backgroundColor="#ffe9e9" fontSize={buttons.yes.size} disabled={isDisabledYes}/>
    <Button text={buttons.no.label} onClick={handleNoClick} backgroundColor="#ffe9e9" fontSize={buttons.no.size} disabled = {isDisabledNo}/>  

  </div>
</div>

<style>
  .picture {
    display: flex;
    justify-content: center;
    height: 200px;
  }
  img {
    height: 300px;
  }
  h2 {
    font-size: 3rem;
    color: #660708;
    font-family: 'Comic Sans MS', cursive, sans-serif;
   /* Comic Sans MS font */
  }
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
