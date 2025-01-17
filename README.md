# Chrome Extention for Privacy from Image Recognition Systems through Adversarial Evasion

This project started off as a NUS Hack n Roll Hackathon project by Ang Ming Liang, New Jun Jie, Chua Bing Quan and Toh Bing Cheng. It applies adversarial patches and noise to images to reduce the effectiveness of public machine learning scrapers – empowering individuals to fight against modern invasion of data privacy. Essentially, to the user it means that it will mask your uploaded image from image recognition systems while appearing the same to the human eye.

The project is currently maintained here and further researched on by AI researcher Ang Ming Liang (@Neoanarika)

## Problem we are solving
In January 2019 IBM released a data set of almost a million photos, scraped from the photo-sharing website Flickr without consent from the subjects and the photographers, and pitched this as part of efforts to reduce the problem of bias within face recognition. 

Social media platforms run widespread image recognition systems on uploaded images, and are currently doing it so well that Facebook could use those systems to contribute to fighting revenge porn. 

Some might think these image recognition systems run on public image data are an infringement of their privacy.

## Solution
Our solution to this social problem is an A.I. Blocker, to trick the algorithms into thinking your photos mean something else. We present a Chrome extension that “masks” your photos, so that machine learning algorithms classify them wrongly, yet appear completely the same to the human eye.

## Technical Description
The user is given 2 choices: apply an Adversarial Patch to his/her image or evenly distribute Adversarial Noise across the image. For the Adversarial Patch, the extension adds a patch on the image provided that causes a general object recognition classifier to misclassify an image.[2] The patch is made by applying expectation over transformation, over a random area of the image. For the Adversarial Noise, the extension makes quasi-imperceptible changes to the image such that a machine learning model classifies it incorrectly by using a single gradient ascent step, also know as a "fast gradient sign method".[3] While both approaches typically require a known existing neural network architecture to compute their adversarial attacks, a.k.a. a white box attack, they have been shown to work well on black box neural network architectures as well.[3]

## Future Work
Our A.I. Blocker performs less effectively against some adversarial defenses, e.g. Robust Optimization and certificates.[4] To overcome this, we can apply 2nd-order gradient information in our future work to generate better-performing adversaries against these defenses. One feature that we did not manage to fully implement was a Universal Adversarial Attack to pre-compute and transform the images in a O(1) constant-time operation for the adversarial step.[1] However, this comes at the expense of less robust A.I. Blocker. Other than improvements to the Adversarial Noise approach, there is also room for improvement for the Adversarial Patch approach. One such improvement can be the use of clever geometry to blend the patch into the image more seamlessly, such as an Adversarial Frame around text. There are also better software engineering practices to implement the backend to reduce the number of times that TensorFlow, VGG and DenseNet are loaded in.


## Results
![ai blocker examples](https://user-images.githubusercontent.com/27071473/51434321-0e7a9780-1c99-11e9-93ee-48b866c292d9.png)

## References
1. "Universal Adversarial Perturbations." 9 Mar. 2017, https://arxiv.org/abs/1610.08401v3.
2. "Adversarial Patch." 27 Dec. 2017, https://arxiv.org/abs/1712.09665.
3. "Explaining and Harnessing Adversarial Examples." 20 Mar. 2015, https://arxiv.org/abs/1412.6572.
4. "Towards Deep Learning Models Resistant to Adversarial Attacks." 9 Nov. 2017, https://arxiv.org/abs/1706.06083.
