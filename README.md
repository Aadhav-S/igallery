# Ex.08 Design of Interactive Image Gallery
## Date:16/12/2006

## AIM:
To design a web application for an inteactive image gallery with minimum five images.

## DESIGN STEPS:

### Step 1:
Clone the github repository and create Django admin interface.

### Step 2:
Change settings.py file to allow request from all hosts.

### Step 3:
Use CSS for positioning and styling.

### Step 4:
Write JavaScript program for implementing interactivity.

### Step 5:
Validate the HTML and CSS code.

### Step 6:
Publish the website in the given URL.

## PROGRAM :
```
index.html

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Document</title>
</head>
<body>
    

<div class="wrapper">
  <div><img src="https://images.unsplash.com/photo-1527576539890-dfa815648363?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI1NjV8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1497334251732-c0eb68e26827?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI1OTV8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1501681506726-610246d81ade?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI3NTV8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1493397212122-2b85dda8106b?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI1OTV8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1548248823-ce16a73b6d49?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI4MDJ8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1518005020951-eccb494ad742?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI0NzJ8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1548318281-7da3085ce691?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI0OTV8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1523274158540-2aa98c15ec26?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU4OTI1OTV8&ixlib=rb-4.0.3&q=85"></div>
  <div><img src="https://images.unsplash.com/photo-1532456745301-b2c645d8b80d?crop=entropy&cs=srgb&fm=jpg&ixid=M3wzMjM4NDZ8MHwxfHJhbmRvbXx8fHx8fHx8fDE3MjU5MDQ3Nzd8&ixlib=rb-4.0.3&q=85"></div>
</div>
</body>
</html>

style.css

.wrapper{
    --_gap: .5rem;
    --_offset: 10%;
    --_offset-1: calc(var(--_offset) * 1);
    --_offset-2: calc(var(--_offset) * 2);
    --_offset-3: calc(var(--_offset) * 3);
    --_offset-7: calc(var(--_offset) * 7);
    --_offset-8: calc(var(--_offset) * 8);
    --_offset-9: calc(var(--_offset) * 9);
      
    width: calc(100% - 4rem);
    max-width: 800px;
    margin: 2rem auto;
    color: white;
    font-family: system-ui;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 0 var(--_gap);
    pointer-events: none;
    transform-style: preserve-3d;
  }
  .wrapper > div{
    position: relative;
    pointer-events: auto;
    aspect-ratio: 1;
    transition: scale 500ms ease-in-out, filter 500ms ease-in-out, clip-path 500ms ease-in-out 500ms;
    clip-path: polygon(var(--_clip-path));
    transform: translate3d(0,0,0);
  }
  .wrapper img{
    width: 100%;
    height: 100%;
    object-fit: cover;
    display: block;
  }
  .wrapper > div:nth-child(n+4){
   margin-top: calc(var(--_offset-3) * -1 + var(--_gap));
  }
  /* define clip-path custom properties */
  .wrapper > div:nth-child(1){ --_clip-path: 0 0, 100% 0, 100% var(--_offset-9), 0 100%;}
  .wrapper > div:nth-child(2){ --_clip-path: 0 0, 100% 0, 100% var(--_offset-8), 0 var(--_offset-9);}
  .wrapper > div:nth-child(3){ --_clip-path: 0 0, 100% 0, 100% var(--_offset-7), 0 var(--_offset-8);}
    
  .wrapper > div:nth-child(4){ --_clip-path: 0 var(--_offset-3), 100% var(--_offset-2), 100% var(--_offset-8), 0 var(--_offset-7);}
  .wrapper > div:nth-child(5){ --_clip-path: 0 var(--_offset-2), 100% var(--_offset-1), 100% var(--_offset-9), 0 var(--_offset-8);}
  .wrapper > div:nth-child(6){ --_clip-path: 0 var(--_offset-1), 100% 0%, 100% 100%, 0 var(--_offset-9);}
  
  .wrapper > div:nth-child(7){ --_clip-path: 0 0%, 100% var(--_offset-1), 100% 100%, 0 100%;}
  .wrapper > div:nth-child(8){ --_clip-path: 0 var(--_offset-1), 100% var(--_offset-2), 100% 100%, 0 100%;}
  .wrapper > div:nth-child(9){ --_clip-path: 0 var(--_offset-2), 100% var(--_offset-3), 100% 100%, 0 100%;}
  
  
  .wrapper > div:hover{
    transition: scale 500ms ease-in-out, filter 500ms ease-in-out, clip-path 500ms ease-in-out 500ms;
    scale: 1.3;
    --_clip-path: 0 0, 100% 0, 100% 100%, 0 100%;
    z-index: 100;
    opacity: 1;
  }
  
  .wrapper:has(:hover) > div:not(:hover){
    filter: grayscale(1) blur(3px);
    opacity: .5;
    scale: 0.9;
  }
  .wrapper > div:not(:hover) {
    /*animation: zIndexHack 1000ms;*/
  
  }
  
  @keyframes zIndexHack {
    0%, 100% { z-index: 100; }
  }
  /* none of this CSS is relevant to the wave animation */
  :root{
    --clr-bg: #222;
    --clr-txt: #F5F5F5;
    --clr-primary: #F5F5F5;
    --clr-secondary: #38BDF8;
    --clr-button: #0369A1;
  }
  html{
    background-color: var(--clr-bg);
    font-family: system-ui;
    color: var(--clr-txt);
  }
  
  body{
    min-height: 100svh;
    color: var(--clr-primary);
    padding: 1rem;
  }
  body::after{
    content: '';
    position: absolute;
    top: 1rem;
    left: 1rem;
    width: 32px;
    height: 32px;
    background-size: cover;
    background-image: url('data:image/svg+xml,<svg id="logo" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 100 100" version="1.1"><g id="surface1"><path fill="rgb(175, 208, 84)" d="M 47.894531 0.789062 C 46.320312 0.878906 45.480469 0.949219 44.601562 1.042969 C 37.023438 1.863281 29.746094 4.394531 23.386719 8.414062 C 20.214844 10.421875 17.402344 12.65625 14.757812 15.285156 C 7.773438 22.222656 3.027344 30.992188 1.113281 40.5 C -0.460938 48.332031 -0.132812 56.378906 2.070312 64.003906 C 4.0625 70.890625 7.507812 77.195312 12.277344 82.675781 C 16.65625 87.714844 22.109375 91.898438 28.074219 94.804688 C 37.914062 99.59375 49.078125 101.03125 59.875 98.886719 C 69.480469 96.976562 78.265625 92.300781 85.253906 85.371094 C 92.304688 78.386719 97.027344 69.65625 98.960938 60.039062 C 99.636719 56.675781 99.902344 53.996094 99.902344 50.285156 C 99.902344 47.910156 99.855469 46.925781 99.660156 45.128906 C 98.671875 35.808594 95.136719 27.136719 89.324219 19.773438 C 86.917969 16.722656 83.851562 13.675781 80.777344 11.285156 C 75.664062 7.304688 69.949219 4.410156 63.695312 2.628906 C 60.5625 1.742188 57.058594 1.128906 53.609375 0.867188 C 52.796875 0.804688 48.566406 0.746094 47.894531 0.789062 Z M 54.105469 24.300781 C 54.105469 24.355469 53.550781 25.921875 52.875 27.773438 L 51.636719 31.148438 L 41.390625 31.148438 C 34.375 31.148438 31 31.167969 30.683594 31.210938 C 27.867188 31.601562 25.414062 33.695312 24.371094 36.621094 C 24.054688 37.503906 23.910156 38.265625 23.839844 39.371094 C 23.800781 40.046875 23.789062 43.769531 23.804688 50.574219 C 23.828125 61.464844 23.816406 60.867188 24.101562 62.066406 C 24.316406 62.976562 24.832031 64.132812 25.339844 64.875 C 26.515625 66.597656 28.074219 67.726562 29.9375 68.203125 C 30.679688 68.394531 31.542969 68.433594 34.851562 68.433594 C 37.878906 68.433594 37.960938 68.441406 37.925781 68.542969 C 37.90625 68.601562 37.34375 70.148438 36.671875 71.972656 L 35.460938 75.296875 L 32.726562 75.296875 C 30.136719 75.296875 29.960938 75.285156 29.269531 75.164062 C 26.808594 74.714844 24.59375 73.707031 22.644531 72.152344 C 22.015625 71.648438 20.859375 70.496094 20.335938 69.847656 C 18.960938 68.15625 17.824219 65.824219 17.285156 63.601562 C 16.824219 61.660156 16.835938 62.175781 16.859375 49.355469 C 16.882812 36.71875 16.847656 37.765625 17.292969 35.953125 C 17.882812 33.523438 18.941406 31.398438 20.515625 29.5 C 21.140625 28.746094 21.625 28.257812 22.417969 27.597656 C 24.695312 25.699219 27.460938 24.53125 30.316406 24.265625 C 30.589844 24.234375 36.054688 24.210938 42.460938 24.207031 C 53.515625 24.199219 54.105469 24.207031 54.105469 24.300781 Z M 66.320312 24.363281 C 69.789062 24.90625 72.703125 26.371094 75.039062 28.757812 C 76.65625 30.402344 77.730469 32.21875 78.382812 34.417969 C 78.683594 35.445312 78.824219 36.347656 78.867188 37.523438 C 78.964844 40.515625 78.066406 43.320312 76.21875 45.777344 C 75.949219 46.136719 75.707031 46.445312 75.675781 46.460938 C 75.558594 46.539062 75.636719 46.605469 76.246094 47 C 80.933594 50.003906 83.621094 55.320312 83.308594 60.960938 C 83.027344 65.992188 80.328125 70.570312 76.113281 73.175781 C 74.453125 74.199219 72.570312 74.894531 70.546875 75.21875 L 69.757812 75.347656 L 56.425781 75.363281 L 43.085938 75.386719 L 43.273438 74.878906 C 43.371094 74.601562 43.949219 73.027344 44.546875 71.386719 L 45.640625 68.40625 L 57.613281 68.375 L 69.582031 68.347656 L 70.167969 68.191406 C 72.121094 67.652344 73.628906 66.617188 74.753906 65.019531 C 75.40625 64.097656 75.960938 62.777344 76.175781 61.632812 C 76.328125 60.832031 76.328125 59.308594 76.175781 58.503906 C 75.867188 56.859375 75.085938 55.316406 73.960938 54.152344 C 72.835938 52.976562 71.722656 52.308594 70.191406 51.894531 L 69.582031 51.730469 L 52.117188 51.703125 L 34.65625 51.671875 L 35.691406 48.835938 C 36.265625 47.273438 36.835938 45.703125 36.96875 45.351562 L 37.207031 44.695312 L 51.269531 44.679688 L 65.328125 44.667969 L 65.941406 44.511719 C 68.972656 43.753906 71.089844 41.820312 71.71875 39.214844 C 71.890625 38.496094 71.898438 37.390625 71.722656 36.699219 C 71.019531 33.839844 68.550781 31.78125 65.21875 31.253906 C 64.984375 31.21875 63.597656 31.171875 62.058594 31.15625 L 59.3125 31.121094 L 60.523438 27.789062 C 61.195312 25.960938 61.769531 24.398438 61.800781 24.324219 L 61.863281 24.183594 L 63.710938 24.21875 C 65.164062 24.242188 65.722656 24.269531 66.320312 24.363281 Z M 66.320312 24.363281 "/></g></svg>');
  }
  
  
  
  h1{
    font-size: 1.2rem;
    font-weight: 500;
    margin-block-end: 1rem;
    text-align: center;
  
  }
  code{
    color: var(--clr-secondary);
    border: 1px solid rgba(from var(--clr-secondary) r g b / .25);
    padding-inline: .25rem;
    border-radius: 5px;
  }

```
## OUTPUT:
![alt text](<Screenshot (37).png>)
![alt text](<Screenshot (38).png>)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
