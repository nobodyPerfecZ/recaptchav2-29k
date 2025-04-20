# ReCAPTCHAv2 Dataset

ReCAPTCHAv2 Dataset is a dataset consisting of images derived from Google's reCAPTCHA v2 system, which is widely used for online human verification.
It contains thousands of reCAPTCHA images, each paired with corresponding labels indicating the presence of specific objects or features (e.g., bicycle, bus, car).
This dataset is intended for educational and research purposes and is particularly suited for tasks such as feature extraction and multi-label image classification.
It contributes to the domain of computer vision by offering real-world, noisy image data representative of visual recognition challenges encountered in reCAPTCHA systems.

## Dataset Structure

- Number of images: 29.568
- Size of each image: 100x100px
- Labels: bicycle, bus, car, crosswalk, hydrant

## Data Distribution

```
| Category  | Column Idx | #Images |
| ----------| ---------- | ------- |
| bicycle   | 0          | 4.994   |
| bus       | 1          | 5.025   |
| car       | 2          | 5.198   |
| crosswalk | 3          | 4.280   |
| hydrant   | 4          | 5.071   |
```

## Data Instances

Each data instance in the dataset is composed of an image and its associated label vector.
The image is represented as a PIL image object, typically in RGB mode and of uniform size (100x100px).
The label is a binary vector indicating the presence (1) or absence (0) of the classes bicycle, bus, car crosswalk and hydrant.

In the following example, the image is associated with a single active label indicating the presence of a hydrant:

```
{
    'image': <PIL.PngImagePlugin.PngImageFile image mode=RGB size=100x100>,
    'labels': [0, 0, 0, 0, 1]
}
```

## Data Splits

Since most images have a single active label, we use class-stratified train-test split based on the primary class of each image.
This approach ensures that the class distribution remains consistent across the training, validation and test datasets.

The final dataset splits are as follows:

| Dataset    | Length |
| ---------- | ------ |
| Train      | 23.637 |
| Validation | 2.957  |
| Test       | 2.957  |

## Social Impact of Dataset

The ReCAPTCHAv2 Dataset offers valuable opportunities for advancing research in computer vision, particularly in tasks related to object detection, multi-label classification, and adversarial robustness.
providing real-world, noisy, and visually diverse examples, it can help researchers develop models that are better equipped to handle real-life complexity, contributing to more accurate and resilient AI systems.
These improvements may enhance accessibility tools, improve safety in autonomous systems, and support the development of AI that can better understand and navigate human environments.

However, the dataset also presents several social risks and ethical concerns:

- **Security and Misuse**: As the dataset is based on CAPTCHA challenges, there is potential for misuse in developing systems designed to bypass human verification mechanisms. While the dataset is provided strictly for educational and research purposes, safeguards must be considered to prevent abuse.

## Discussion of Biases

As the ReCAPTCHAv2 Dataset is derived from Google's reCAPTCHAv2 system, several inherent biases may be reflected in the data:

- **Geographic Bias**: The images may be biased towward urban environments commonly found in North America and Europe, potentially underrepresenting non-Western regions.
- **Object Representation Bias**: Certain object classes (e.g., cars, traffic lights, buses) may be overrepresented, while others may appear less frequently or not at all. This can affect the generalizability of models trained on the dataset.
- **Cultural Context Bias**: The design of reCAPTCHA tasks may implicitly assume familiarity with specific traffic symbols, infrastructure, or object appearances that vary globally.
- **Visual Quality and Noise Bias**: To increase task difficulty, Google's system often introduces visual noise, distortions, or transformations (e.g. blurring, compression artifcats, color space shifts). These manipulations are preserved in the dataset and can impact both human and model performance.

## Contributing

We welcome any contribution to this dataset.
If you have additional images to add or find any errors, please open an issue or submit a pull request.

## Dataset Curators

The ReCAPTCHAv2 Dataset was collected by web scraping from the [Google's reCAPTCHAv2 demo page](https://www.google.com/recaptcha/api2/demo).
The dataset was manually labeled to support multilabel image classification tasks.

> ⚠️ **Disclaimer**: This dataset was created for educational and research purposes only. It is not affiliated with or endorsed by Google or the reCAPTCHA team.

## License

This repository is released under the [MIT License](LICENSE).

Please note that while this project is distributed under an open-source license, the reCAPTCHA images themselves are owned by Google.
Fair Use from Google allows to use this dataset for nonprofit, educational, research and analysis purposes.
