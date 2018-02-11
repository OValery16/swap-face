# swap-face

This is a complete guide for the swap-face algorithm known as deepFakes. 

## Why this project?

The goal of this project is education purpose. The deepFakes project got viral on the internet (with all the moral implication that come with it), but very few people really understand how it works. In fact, it is relatively simple>

The youtube video about deepfake made by Siraj Raval also gives a good insight about deepfakes, and I invite you to check its video.

## Coding Challenge

The coding challenge presented in deepFakes by Siraj Raval.

This coding challenge is to train a swap-face algorithm.

The submission files are the three Ipython Notebooks: 

1.      Training data generation.ipynb
2.      Train.ipynb
3.      Prediction.ipynb

## James bond swapping-face

I was born in 1988. So for me, James Bond has always been Pierce Brosnan (even Daniel Craig doesn't play that bad). As a result, today we will learn how to train a network that swap the face of Daniel Craig and replace it by Pierce Brosnan. The result can be seen below.

![](image/jamesSwap.png?raw=true)

## What id DeepFakes?

Deepfake is implemented as an autoencoder.
The face of the actor 1 is cropped and aligned to his face. Then the autoencoder learns how to encode and decode (reconstruct) the face. The goal here is to minimize the reconstruction error.

![](image/encoder1.JPG?raw=true)

The face of the actor 2 is cropped and aligned to his face. Then the autoencoder learns how to encode and decode (reconstruct) the face. The goal here is to minimize the reconstruction error. The interesting part is that the encoder is the same for actor 1 and 2.

![](image/encoder2.JPG?raw=true)

The goal is to find a mathematical function that for a face of the actor 1, outputs a face that looks like the actor 2.

Note: these images don t belong to me and comes from the animation in the youtube video about deepfake made by Siraj Raval

## Transfer Learning

In contrast to the base version of Deepfakes, we provide a very convenient way to speed up the training process via transfer learning. The idea is to load the weight of a pre-trained network (for the same network configuration but for another face pair such as Donald ump and Nicolas Cage) These weights are used as a starting point to learn new weight. The network will, therefore, converge faster than if it would be trained from scratch. \n",

More advanced technique exists to apply transfer learning to autoencoder such [here](https://www.ijcai.org/Proceedings/15/Papers/578.pdf)

## The dependencies

Associated with this project, there is a file called "floyd_requirements.txt" which lists all libraries that need to be installed before to run the application.

You install them with sudo pip install <library name>

If you have any problem. Feel free to contact me or post an issue.

The version I release can be run on any computer or virtual machines (as long as the requirement are installed). 

The nice thing is that you can also run it easily on floydhub (which is a cloud GPU company). Please note that I don't work for this company (just that you often need GPU to train such model)

## The weights

You can download the weights [there](https://drive.google.com/file/d/1J1PgGZDCufCxZ6vEwHwnM7czAXjIliH5/view?usp=sharing)

## Result

Input            |  Output
:-------------------------:|:-------------------------:
![](/image/CR_2012.jpg?raw=true)  |  ![](/image/CR_2012_v2.jpg?raw=true)
![](/image/bond.jpg?raw=true)  |  ![](/image/bond_v2.jpg?raw=true)
![](/image/casino_royale_movie_image_james_bond__1_.jpg?raw=true)  |  ![](/image/casino_royale_movie_image_james_bond__1__v2.jpg?raw=true)
![](/image/Casino-Royale-Eva-Green-Daniel-Craig.jpg?raw=true)  |  ![](/image/Casino-Royale-Eva-Green-Daniel-Craig_v2.jpg?raw=true)
![](/image/james-bond-casino-royale.jpg?raw=true)  |  ![](/image/james-bond-casino-royale_v2.jpg?raw=true)

## Moral implication

The goal of this project is education purpose. With AI area, it becomes easy for anyone to fake video, pictures, and news. As someone smart said one day: "With great power comes great responsibility".

## Additional discutions

Autoencoder is great tool for producing images which respect the probability distribution of the original ones. However, I believe that Generative Adversarial Networks (such as cycle-gan) remains a great way to train autoencoder, and surpass the generation capability of standard autoencoder.


