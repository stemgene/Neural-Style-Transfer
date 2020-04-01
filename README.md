# Neural-Style-Transfer

Neural style transfer is an optimization technique that takes as input a content and a style image, and optimizes a target image to resemble the contents of the content image and style of the style image, blend them together so the output image looks like the content image, but “painted” in the style of the style reference image.

In this case, I take an image of the Rash Rhee library as the content, then choose a masterpiece of Wheatfield with Cypresses created by Vincent Van Gogh as the style:

Content:
![content](https://github.com/stemgene/Neural-Style-Transfer/blob/master/image/content_mid.jpeg)

Style:
![Style](https://github.com/stemgene/Neural-Style-Transfer/blob/master/image/style_mid.jpeg)

Neural style transfer is a kind of application of GAN (Generative Adversarial Networks), and the VGG-Net, a model of CNN (Convolutional Neural Network), can be applied as a typical model. The whole process of training can be braked into several steps briefly:
- Step1: Build the model. Extract the intermediate layer values from the VGG-Net. 
- Step2: Calculate style. The style of an image can be described by the means and correlations across the different feature maps. Calculate a Gram matrix that includes this information by taking the outer product of the feature vector. 
- Step3: Extract style and content
- Step4: Run gradient descent. With style and content extractor, implement the style transfer algorithm. In this case, I complete this by calculating the mean square error, then take the weighted sum of these losses.
Step5: Fine tune the network. Decrease the high frequency artifacts using an explicit regularization term on the high frequency components of the image.

The result likes this:
![result]()
