## Inspiration
A close friend of one of our group members was killed by a drunk driver. Getting drunk drivers off the roads will save lives and prevent years of trauma for victims families.
## What it does
The FaceBeer product is a physical device and a website. It is intended to be operated by a business such as a club or bar, as method of monitoring the sobriety of its patrons.
### Device
When a patron wants to enter a bar, they hold the device and press the button which immediately takes a picture of the patron. The device then process the image with a custom-made image classification model, which instantly identifies the patron, eliminating the need for IDs and making it easier for especially inebriated patrons. With the patron identified, they are then prompted to blow into our custom breathalyzer. Their blood alcohol content is then displayed on the screen, and the data is sent to our API.
### Website
The manager of the business can view the sobriety of all patrons [on our website facebeer.net](https://facebeer.net). This website has complete functionality for showing historical data for every patron that has ever used FaceBeer. It allows easy querying of users, viewing data recorded in the past twelve hours, as well as viewing the most inebriated patrons. The manager can then use this information to perform the necessary actions to keep drunk drivers from getting into their cars, thereby keeping drunk drivers off the road with the help of FaceBeer.
## How we built it
### Device
#### Machine Learning
We trained a custom MobileNet V2 image classification model with the TensorFlow 2 API. We created a dataset of 400 images with our infrared camera, taking 1000 pictures of the 4 group members. This model reached 99% accuracy on the test dataset. The model was converted to the TensorFlow Lite format to be optimized for mobile computing on the Raspberry Pi.
#### Finite State Machine
We created a large state machine to handle the different stages of use. It effectively navigates waiting for the user to press the button, taking the picture, recognizing the face, recording blood alcohol content, sending data to the database, and displaying instructions on the OLED display.
#### Hardware
We used the following equipment:
- Raspberry Pi
- OLED display
- MQ3 alcohol sensor
- Analog to Digital Converter
- Infrared Camera
- Arcade button

We CAD'd the FaceBeer device in SolidWorks, with special consideration for ergonomics when being used. We included grips designed to be held easily, and an OLED screen for guiding the user. The FaceBeer case was 3D printed in WPI's ColabLab. We soldered our sensors to the Raspberry Pi, and managed the wires inside the 3D printed case.

## Challenges we ran into
- Training a model to be accurate with the user being in a variety of distances away from the camera required us to create a very large dataset (4000 images)
- Creating a secure website involved issuing 

## Accomplishments that we're proud of
We're proud of our entire development process. Over the course of this weekend, we have been able to take this project from a simple idea to a working and polished prototype. In particular, our custom machine learning model, ergonomic CAD design, and secure back-end were tough challenges that our team was able to overcome.

## What we learned
Our greatest learning outcomes throughout this project were due to the exchanging of knowledge between team members. Our team was able to share deep understanding across a variety of topics with each other. This allowed members with weaker understandings in particular areas like machine learning, web development, cybersecurity, and CAD to learn from those with more experience.

## What's next for FaceBeer
We plan to continue working to better refine the accuracy of our alcohol sensor to best estimate the user's BAC. We would also like to conduct local market research to see if any businesses in Worcester would be interested in using our product.
