---
layout: post
title: Pokemon-generator
---
<h1 style="font-size:200%;text-align:center">Using Generative Adversarial Networks to generate Pokemon</h1>

Growing up, I really enjoyed everything about Pokemon. I remember that I was around 11 when my parents bought me my first Pokemon game, Pokemon Ruby. The first Pokemon I chose was the grass-type, Treecko, and then at the second gym I regretted my decision and restarted the game to play with the water-type Mudkip (Because I loved the swimming pool, so it made sense to me as a kid to only have water-type Pokemon). 

I was never a good player competitive player (Yeah, I very often loose, haha!), but one thing I really really like is the design element Pokemon has. As a child, I was very amused by the fact that a Pokemon could be based on a pitcher plant (Victreebel) or a psychic duck that is not actually psychic (Golduck). So, honouring my childhood and my career as a data scientist, I thought I would be a great idea to start a project using Generative Adversarial Networks (Or also known as GANs) to generate new Pokemon. So let's begin!

<h3 style="font-size:200%;text-align:center">GANs</h3>

The first thing I wanted to touch on is Generative Adversarial Models. Briefly speaking, a Generative Adversarial Network is a machine learning framework in which 2 Neural Networks are adversaries (as the name indicates). And why are they opponents?, you may ask. Basically, one of the networks is in charge of generating new or 'fake' images and the other one is in charge of evaluating if the image is 'fake' or not. The first network is called the generator and the second is called the discriminator. And the whole point of the framework is that the generator could generate 'fake' images in a way in which the discriminator would not be able to detect that the image is 'fake'.

Or in the words of Tensorflow
![GANs](https://github.com/tensorflow/docs/raw/3082041fb5ef2b29217584659bc43d89602d57cf/site/en/tutorials/generative/images/gan1.png)

<h3 style="font-size:200%;text-align:center">Pokemon data</h3>

Well, for those of you who don't know what a Pokemon is here is sample of the images I used

![Pokemon_sample](../images/pokemon_sample.PNG)

Please, play a Pokemon game. Also, this data contains almost 900 Pokemon from the first 8 generations and it was scrapped from [pokemon.com](https://www.pokemon.com/us/pokedex/). I did not upload the images to the repo. 


<h3 style="font-size:200%;text-align:center">The work</h3>

Just briefly, using the link above, I created a GAN with the images in 'RGBA' mode. I resized the images to 80x80 so that they were easier to handle. In addition, I trained the model for 700 epochs using google colab. As a first result, this is what I got

![result](../images/results.PNG)

The one on the right looks like Butterfree but not as clear.

As you can see, there is still a lot of room for improvement. Maybe, trying to change the architecture could help (Also, I would be interested to know if there is any pretrained NN that involves Pokemon). Nonetheless, I see that there are interesting shapes that are starting to be created, the gif looks really artsy and I am enjoying watching it. Maybe running it for more epochs could help too. 

Overall, I am really liking this project so I think I will keep on improving it. If you are insterested in the code, here is the link to the [repo](https://github.com/AndresPitta/P02_Pokemon-merger). Stay tuned for more work!




