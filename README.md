# Ex.08 Design of Interactive Image Gallery
## Date:16/12/2024

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
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Interactive 3x2 Grid Gallery</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #f4f4f4;
        }

        .gallery {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 10px;
            width: 80%;
            max-width: 800px;
        }

        .gallery-item {
            position: relative;
            overflow: hidden;
            cursor: pointer;
        }

        .gallery-item img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s ease;
        }

        .gallery-item:hover img {
            transform: scale(1.1);
        }

        .gallery-item .overlay {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.5);
            color: white;
            display: flex;
            justify-content: center;
            align-items: center;
            opacity: 0;
            transition: opacity 0.3s ease;
        }

        .gallery-item:hover .overlay {
            opacity: 1;
        }

        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            justify-content: center;
            align-items: center;
        }

        .modal img {
            max-width: 90%;
            max-height: 90%;
        }

        .modal .close {
            position: absolute;
            top: 20px;
            right: 20px;
            color: white;
            font-size: 24px;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <div class="gallery">
        <div class="gallery-item" data-image="https://via.placeholder.com/600x400?text=Image+1">
            <img src="image 1.jpg" alt="Image 1">
            <div class="overlay">Image 1</div>
        </div>
        <div class="gallery-item" data-image="https://via.placeholder.com/600x400?text=Image+2">
            <img src="image 2.jpg" alt="Image 2">
            <div class="overlay">Image 2</div>
        </div>
        <div class="gallery-item" data-image="https://via.placeholder.com/600x400?text=Image+3">
            <img src="image 3.jpg" alt="Image 3">
            <div class="overlay">Image 3</div>
        </div>
        <div class="gallery-item" data-image="https://via.placeholder.com/600x400?text=Image+4">
            <img src="image 4.jpg" alt="Image 4">
            <div class="overlay">Image 4</div>
        </div>
        <div class="gallery-item" data-image="https://via.placeholder.com/600x400?text=Image+5">
            <img src="image 5.jpg" alt="Image 5">
            <div class="overlay">Image 5</div>
        </div>
        <div class="gallery-item" data-image="https://via.placeholder.com/600x400?text=Image+6">
            <img src="image 6.jpg" alt="Image 6">
            <div class="overlay">Image 6</div>
        </div>
    </div>

    <div class="modal" id="modal">
        <span class="close" id="closeModal">&times;</span>
        <img id="modalImage" src="" alt="">
    </div>

    <script>
        const galleryItems = document.querySelectorAll('.gallery-item');
        const modal = document.getElementById('modal');
        const modalImage = document.getElementById('modalImage');
        const closeModal = document.getElementById('closeModal');

        galleryItems.forEach(item => {
            item.addEventListener('click', () => {
                const imageSrc = item.getAttribute('data-image');
                modalImage.src = imageSrc;
                modal.style.display = 'flex';
            });
        });

        closeModal.addEventListener('click', () => {
            modal.style.display = 'none';
        });

        modal.addEventListener('click', (e) => {
            if (e.target === modal) {
                modal.style.display = 'none';
            }
        });
    </script>
</body>
</html>

```
## OUTPUT:
![alt text](<Screenshot (50).png>)
![alt text](<Screenshot (51).png>)

## RESULT:
The program for designing an interactive image gallery using HTML, CSS and JavaScript is executed successfully.
