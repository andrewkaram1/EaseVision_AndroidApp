[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]


<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/othneildrew/Best-README-Template">
    <img src="logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Ease Vision</h3>

  <p align="center">
   Ease Vision has been crafted as an innovative way to assess a population’s temperature in real time by collecting the data of individuals walking by. 
    <br />
    <a href="https://github.com/andrewkaram1/EaseVision_AndroidApp/blob/master/README.md"><strong>Explore the docs »</strong></a>
    <br />
    <br />
    <a href="https://www.dropbox.com/s/ig9fvz40e18cnga/HIGHQuality_Final.mp4?dl=0">View Demo</a>
    ·
    <a href="https://github.com/andrewkaram1/EaseVision_AndroidApp/issues">Report Bug</a>
    ·
    <a href="https://github.com/andrewkaram1/EaseVision_AndroidApp/issues">Request Feature</a>
  </p>
</p>



<!-- TABLE OF CONTENTS -->
## Table of Contents

* [About the Project](#about-the-project)
  * [Built With](#built-with)
* [Getting Started](#getting-started)
  * [Prerequisites](#prerequisites)
  * [Dependencies](#dependencies)
  * [Installation](#installation)
* [Usage](#usage)
* [Roadmap](#roadmap)
* [Contributing](#contributing)
* [License](#license)
* [Contact](#contact)
* [Acknowledgements](#acknowledgements)



<!-- ABOUT THE PROJECT -->
## About The Project
The application works collaboratively with the data being provided by an OPENMV H7 camera running an infrared imaging sensor, Lepton 3.5, with a Wi-Fi shield. The OPENMV cam is an IOT device programmed in micro python. When placed in a public setting, the camera utilizes the average screen temperature and evaluates it to determine if a being is present. Once the program identifies a person(s), it saves the IR frame and sends the image to a Raspberry Pi. The microcontroller then makes an HTTP post request call to the IBM Watson visual recognition service, which analyzes the image to locate a face(s). The Raspberry Pi is essential to the system since the OpenMV CAM lacks the ability to perform certain API calls. On return, the camera will receive the coordinates of where the face(s) were present in the frame. These coordinates are then utilized to give a mean temperature reading of the returned area. The OpenMV camera then evaluates if the assessed temperature is considered elevated or non-elevated based on WebMD’s fever temperature reading. This data then goes into a count-based variable, which on interval is pushed to IOT platform. This IOT service will receive not only the number of elevated and non-elevated temperature readings, but all information about the device’s specific location. On the other hand, the Android app has been programmed in Java to receive all the data from the IOT platform. On the start screen the application prompts the user for their country, state, and city. After all the information is filled, the selected city’s data as well as a surrounding map is displayed. The severity of the location is shown by a red marker, additionally, in the left corner the number of elevated vs non elevated individuals is further dissected.  The collaborative work between the OpenMV CAM running a Lepton sensor has much potential in accurately visualizing areas of high risk as well as predicting future outbreaks. Due to my financial status I am currently limited to one camera, but I strongly believe the capabilities of this application to help our society immensely. I strive to have these sensors throughout cities, malls, and populated areas of interest across the world. This would gather much data on a population allowing one to understand today’s situation and predict tomorrows. Currently, the majority of people rely on the number of confirmed cases to assess the situation of a specific place. However, the number of cases will not pinpoint a live exact location’s severity nor tell you who is currently ill and not quarantining. This information would not only assist common persons, but moreover, essential workers and government officials to best prepare for the next day. 

### Built With
![layout](layout.PNG?raw=true "Optional Title")
This project collaboralively with a [OPENMV H7 Camera]("https://github.com/andrewkaram1/EaseVision_OpenMV-Cam"), [Rabserry PI](https://github.com/andrewkaram1/EaseVision-RasberryPI). In combination the system leverages cloud services required for the project. The cloud computed data is forwarded to an application on the [Android Platform](https://github.com/andrewkaram1/EaseVision_AndroidApp) for presentation.

[IBM Cloud Service](https://www.ibm.com/cloud/services)
  * [IBM Watson Visual Recognition](https://www.ibm.com/cloud/watson-visual-recognition)
  * [IBM Watson IOT](https://www.ibm.com/internet-of-things)
[Google Maps](https://developers.google.com/maps/documentation/android-sdk/overview)

<!-- GETTING STARTED -->
## Getting Started
Import the project into Android Studio

### Prerequisites
* [Android Studio]("https://developer.android.com/studio")
* [Google maps API Key]("https://developers.google.com/maps/documentation/android-sdk/overview")
* [IBM IOT Service http link]("https://www.ibm.com/internet-of-things")

### Dependencies
All dependencies are taken care of within the build.gradle
```JS
dependencies {
    implementation fileTree(dir: "libs", include: ["*.jar"])
    implementation 'androidx.appcompat:appcompat:1.1.0'
    implementation 'com.google.android.gms:play-services-maps:17.0.0'
    implementation("com.squareup.okhttp3:okhttp:4.8.0")
    implementation 'androidx.constraintlayout:constraintlayout:1.1.3'
    testImplementation 'junit:junit:4.12'
    androidTestImplementation 'androidx.test.ext:junit:1.1.1'
    androidTestImplementation 'androidx.test.espresso:espresso-core:3.2.0'

}
```

### Installation
1. Clone the repo
```sh
git clone https://https://github.com/andrewkaram1/EaseVision_AndroidApp
```
2. Enter your Google maps API key in `google_maps_ap.xml`
```JS
<string name="google_maps_key" templateMergeStrategy="preserve" translatable="false">KEY HERE</string>
</resources>';
```
2. Enter your IBM watson IOT HTTP request URLS in the `infoActivity.java`

<!-- USAGE EXAMPLES -->
## Usage

![layout](concept.PNG?raw=true "Optional Title")

For more examples, please refer to the [Documentation](https://github.com/andrewkaram1/EaseVision_AndroidApp/blob/master/README.md)



<!-- ROADMAP -->
## Roadmap

![Alt text](FINAL%20AK-1.jpg?raw=true "Optional Title")



<!-- CONTRIBUTING -->
## Contributing

Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request



<!-- LICENSE -->
## License

Distributed under the MIT License. See `LICENSE` for more information.



<!-- CONTACT -->
## Contact

Andrew Karam - Andrewkaram44@gmail.com

Project Link: [https://github.com/andrewkaram1/EaseVision_AndroidApp](https://github.com/andrewkaram1/EaseVision_AndroidApp)



<!-- ACKNOWLEDGEMENTS -->
## Acknowledgements
* [OpenMV](https://openmv.io)
* [IBM](https://www.ibm.com/cloud)
* [Google Maps](https://developers.google.com/maps/documentation/android-sdk/start)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[issues-shield]: https://img.shields.io/github/issues/andrewkaram1/EaseVision_AndroidApp
[issues-url]:  https://github.com/andrewkaram1/EaseVision_AndroidApp/issues
[license-shield]: 	https://img.shields.io/github/license/andrewkaram1/EaseVision_AndroidApp
[license-url]: https://github.com/andrewkaram1/EaseVision_AndroidApp/blob/master/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=flat-square&logo=linkedin&colorB=555
[linkedin-url]: https://www.linkedin.com/in/andrew-karam-b48a77170
