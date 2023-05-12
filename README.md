# colab_scripts
Assortment of colab scripts. Most are meant to apply deep learning models from Hugging Face. There are a few misc. scripts like twitter edge list generation.

These are copies of the colab scripts, meant to endure. There is a less stable copy ovailable on google drive [here](https://docs.google.com/document/d/18cNWM8iu7hVXn3DdHBN3mmuTbZwoJ_AzTdk71oBOLeQ/edit?usp=sharing)



_____________
## Image analysis

This folder has scripts meant to apply to still images. Typical usage of these models is to caption a scene, segment objects in an image, or label objects within a scene. The technology is less skilled at attributing sentiment to a visual scene, but feel free to get some text captions and try something like topic modeling to parse through large image datasets. 


- OWL object detection - This model searches for objects in an image that match the query you specify. You simply give it a list of items described in natural language. Pay attention whatever threshold you set for the confidence scores. 


- YOLO object detection - Model returns a bounding box around every item it finds that matches the list of items it has been trained to locate. Unlike the OWL model, the list of queries cannot be changed right when you download the model from hugging face. Look into fine-tuning in order to pull off a longer project. 


- Classify from image link - These take images and output a preset class label to match whatever is in the image. There are two models - the base script uses ResNet, and the second script uses a larger model called VIT. These may only be useful for education/experimentation because the classes are preset - look into fine-tuning in order to pull off a longer project. 


- Get segmentation masks - This model breaks an image into many components (basically find objects like the magic wand tool in photoshop). It outputs these objects in a list of masks, where each mask is the pixel coordinates of the image with the area of the object set to true and the rest set to false. You can overlay masks over the image to check that the model is working, but may be useful for other types of analysis.




________________
## Text analysis
This folder has a range of tools, mostly classifiers that output some preset quality about a piece of text. These models do best if they are applied to the same domain they were trained on. So apply twitter models to twitter text. Try to use models trained on the most recent text, as old models will not know what to do with new words. 

- Basic sentiment analysis: This classifies text into a category of positive, neutral, and negative. Confidence scores are provided for each determination. There is a script for twitter text and for general english. 


- Emotion sentiment analysis: This classifies text into “emotion” categories. There is one script that has 4 emotion labels, and one that has 6 (closer to the 7 emotions agreed on by psych). Since not all text displays an emotion, it is a good idea to drop all classifications under a certain  threshold of confidence score.


- Hate speech: This makes a binary classification of “hate” or “not hate”. This will basically function like a complicated profanity detector - the nuances of offensive speech will not be picked up on unless someone explicitly taught the comparison in the training data. If it's classified as hate, it’s probably offensive, but if it’s classified as not hate, the model may have missed out on some context. And don’t expect it to pick up on the subtleties of minority groups reclaiming slurs. 


- 5 star review: This gives product ratings from 1-5 stars. Do not use it for creative purposes - it’s just to gauge how much a user liked a product.
 
- Topic modeling - the only unsupervised tool available. It will represent samples of text using the same technology as the Language models making waves in 2023. Then it will cluster the samples into a hierarchical tree. From there, it’s easy to pick how “finely branched” you want the topic tree to be, to control the granularity of your topics.





