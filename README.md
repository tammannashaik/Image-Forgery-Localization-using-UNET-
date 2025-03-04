Recent years have seen a rapid spread of unauthenticated information from the images that are manipulated. The technology has progressed from identifying whether the image is forged or not to identifying the forged portion of an image which is the localization of the forged image. Segmentation plays a major role in identifying this forged portion.


In recent years, deep learning-based approaches have gained prominence due to their ability to handle complex manipulation techniques and their adaptability to diverse scenarios. The choice of algorithm depends on factors such as the specific type of forgery being targeted, the available dataset, computational resources, and the desired level of localization accuracy. Block Matching Algorithms identify duplicated or copied regions by searching for similar blocks of pixels within an image. Convolutional Neural Networks (CNNs) are extensively used for image forgery localization. They can be trained to generate pixel-wise probability maps that indicate the likelihood of forgery at each pixel. The model's output map highlights manipulated regions.


In this proposed method, U-Net architecture, designed for image segmentation which is effective in localizing manipulated regions is used for Image Forgery Localization. Its skip connections help capture detailed information and context, enabling accurate localization. The concept behind Localizing the forged portion of the image shall be discussed in subsequent Sections


The desired model should predict the masks for the given image. Therefore, it should contain an encoder-decoder architecture. As we are trying to highlight the tampered regions in the given image, the model needs to segment the image into two classes: one for the tampered region (dark colour) and another for the untouched region (light colour).


. U-Net architecture is characterized by its U-shaped layout, which consists of an encoder path and a corresponding decoder path, along with skip connections that link corresponding layers between the two paths. First path is the contraction path (also called as the encoder) which is used to capture the context in the image. The encoder is just a traditional stack of convolutional and max pooling layers. The second path is the symmetric expanding path (also called as the decoder) which is used to enable precise localization using transposed convolutions. Thus it is an end-to-end fully convolutional network (FCN), i.e. it only contains Convolutional layers and does not contain any Dense layer because of which it can accept images of any size.
