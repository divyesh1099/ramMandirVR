# Augmented Reality Ram Mandir Project

This project demonstrates how to set up a web-based augmented reality (AR) experience using AR.js with A-Frame. The experience is triggered by a custom "RAM" marker, which, when scanned by the device's camera, will display a 3D model of the Ram Mandir.

## Demo

Here's a working demo of the VR: 

https://github.com/divyesh1099/ramMandirVR/assets/65925922/a76ecbd0-77de-4344-a8b1-e7d09e8557b8

## Prerequisites

- Basic knowledge of HTML and JavaScript.
- A modern web browser with support for WebXR or WebVR, such as the latest versions of Chrome or Firefox.
- Node.js and npm installed (for setting up a local server).
- A text editor for editing code files (e.g., Visual Studio Code).

## Setup Instructions

### 1. Environment Setup

Before you begin, make sure Node.js is installed on your computer. You will need it to install `http-server` for local development.

### 2. Project Structure

Here is the basic structure of the project files and directories:

```plaintext
/ramMandirVR/
|-- index.html
|-- yourModel.glb
|-- pattern.patt
```

### 3. Installation

#### Install `http-server`:

```bash
npm install -g http-server
```

### 4. Create the Marker

Design a simple black and white image with the word "RAM" and use the [AR.js Marker Training](https://jeromeetienne.github.io/AR.js/three.js/examples/marker-training/examples/generator.html) page to generate a `.patt` file.

### 5. Building the AR Scene

Create an `index.html` file and set up your scene with A-Frame and AR.js:

```html
<!DOCTYPE html>
<html>
<head>
    <title>AR Ram Mandir Project</title>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <script src="https://raw.githack.com/AR-js-org/AR.js/3.3.0/aframe/build/aframe-ar.js"></script>
</head>
<body style="margin: 0; overflow: hidden;">
    <a-scene embedded arjs='sourceType: webcam;'>
        <a-marker type='pattern' url='./ram.patt'>
            <a-entity 
                gltf-model="./yourModel.glb" 
                scale="0.01 0.01 0.01" 
                position="0 0 0">
            </a-entity>
        </a-marker>
        <a-entity camera></a-entity>
    </a-scene>
</body>
</html>
```

### 6. Running the Project

Navigate to your project directory in the command line or terminal and start the server with `http-server`:

```bash
http-server
```

Open your web browser and go to `http://localhost:8080` to view the project. Point your device’s camera at your custom "RAM" marker to view the 3D model.

## Troubleshooting

If the model does not appear when the marker is detected:
- Check that the marker design is clear and simple.
- Ensure the `.patt` file is correctly placed in the project directory and properly linked in your `index.html`.
- Adjust lighting conditions to make sure the marker is well-lit.
- Verify the scale and position of the model in your A-Frame scene.

## Resources

- [A-Frame Documentation](https://aframe.io/docs/)
- [AR.js Documentation](https://github.com/AR-js-org/AR.js)
- [Node.js](https://nodejs.org/)

## License
Read more in [LICENSE](LICENSE)
