# Image Changer with Haptic Feedback

This React Native application allows users to cycle through a collection of images with the added feature of haptic feedback upon each image change.

## Features

- **Image Carousel**: Navigate through a predefined set of images by tapping the "Next Image" button.
- **Haptic Feedback**: Experience tactile feedback with each image transition, enhancing user interaction.

## Prerequisites

- **Node.js**: Ensure you have Node.js installed. You can download it from [nodejs.org](https://nodejs.org/).
- **Expo CLI**: Install Expo CLI globally using npm:

  ```bash
  npm install -g expo-cli

Installation
Clone the Repository:

bash
Copy code
git clone https://github.com/Adity-aprasad/ImagechangerWithHaptic_feedback.git
cd ImagechangerWithHaptic_feedback
Install Dependencies:

bash
Copy code
npm install
Start the Application:

bash
Copy code
expo start
This will launch the Expo development server. You can then use the Expo Go app on your mobile device or an emulator to view the application.

Usage
Navigate Images: Press the "Next Image" button to cycle through the images.
Experience Haptic Feedback: Each press provides haptic feedback, enhancing the interactive experience.
Code Overview
Image Data: The application uses an array of image objects, each containing an id and the image source.

javascript
Copy code
const data = [
  { id: '1', image: require('./images/image1.jpg') },
  { id: '2', image: require('./images/image2.jpg') },
  // Add more images as needed
];
State Management: The useState hook manages the currently displayed image.

javascript
Copy code
const [presentImage, setPresentImage] = useState(data[0]);
Change Image Function: The changeImage function updates the displayed image and triggers haptic feedback.

javascript
Copy code
const changeImage = () => {
  let curr = data.findIndex(item => item.id === presentImage.id);
  let nextIndex = (curr + 1) % data.length;
  setPresentImage(data[nextIndex]);
  Haptics.impactAsync(Haptics.ImpactFeedbackStyle.Medium);
};
Dependencies
React Native: A framework for building native apps using React.
Expo: A platform for universal React applications.
Expo Haptics: Provides haptic feedback for iOS and Android devices.
Contributing
Contributions are welcome! Please fork the repository and submit a pull request for any enhancements or bug fixes.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Acknowledgements
Expo for providing the development platform.
React Native for the framework.
Expo Haptics for haptic feedback functionality.
