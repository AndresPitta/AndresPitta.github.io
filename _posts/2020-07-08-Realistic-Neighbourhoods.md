---
title: "Realistic-Neighbourhoods"
layout: post
output: pdf_document
---
<h1 style="font-size:200%;text-align:center">Generating Photo Realistic Neighbourhoods using Artificial Intelligence</h1>

On my previous [post](https://andrespitta.github.io/Pokemon-generator/), I decided to use an Artificial Intelligence framework known as Generative Adversarial Networks (GANs) to generate new, never-seen-before Pokemon. Even though I had around 890 images of Pokemon, the results did not generate any clear new Pokemon. This time, in collaboration with a team of 3 more people, I decided to run an improved version of the same algorithm, but in a difference dataset. 

<h3 style="font-size:200%;text-align:center">The Problem</h3>

This problem was proposed by a Capstone partner during my graduate program at UBC. The whole idea was to take a dataset of houses images to generate new, realistic images for a real estate website. This solution would address the issue of having empty thumbnails for some specific pages on the website. It is also worth mentioning that the images are not related to house postings (because we cannot sell a house that does not exist), but it is more related to the aesthetics of the website.

<h3 style="font-size:200%;text-align:center">The data</h3>

Our capstone partner provided to us around 217,000 images of houses as shown below.   

![Houses_sample](../images/sample_image.png)

Most of the pictures contained your typical American house with a big front yard and a family of 8. However, in the dataset we also had images that contained interiors and floorplans, like this one:

![Giraffe_sample](../images/giraffe.jpg)

And I know that giraffes are really cool. Nonetheless, one problem we saw in the previous post is homogeneity. It seems like, when images are not cohesive enough, GANs try to generate images that resemble all of the elements in them. Thus, the team believes that, having a floorplan in the same dataset as an exterior image will result in noisy generated images. In order to solve this problem, using [this code](https://github.com/AndresPitta/MDS-2019-20-capstone-realtor.com/blob/master/src/img_cluster.py), we created 4 clusters as shown here:

![clusters](../images/clusters.PNG)

For this model, for cohesiveness, we used about 100,000 from the exteriors cluster. This is because these images resemble the images that are already in the website.

<h3 style="font-size:200%;text-align:center">The work</h3>

This bit is a little more technical, for those of you who want a little more detail. As mentioned in the previous post, GANs are made of 2 opposing networks: The Generator and The Discriminator. The Generator is in charge of generating images and the Discriminator is in charge of judging whether these images are real or not. The networks are trained for several epochs, in which for each epoch, the networks become better at doing their job. The goal is that, after several epochs, the Generator generates images realistic enough to fool the discriminator.

For this model, we used a conditional GANs, which basically means that the input is a city and the output will be a generated image of that city. The architecture we used for the model is the following:

![architecture](../images/architecture.png)

The final model was run for 3200 epochs using a GPU optimized instance in AWS. Which in a few words means that we had to spend almost 20 hours running the model in AWS. If you want to see the code it is located [here](https://github.com/AndresPitta/MDS-2019-20-capstone-realtor.com/blob/master/src/cdcgans.py)

<h3 style="font-size:200%;text-align:center">The results</h3>

Finally, the results. I promise this part is going to be more interesting haha. As I mentioned before, the network was trained for 200 epochs. For each epoch, the generator became better and better at generating never-seen-before images. Here is an example of what I am saying:  

![gan_process](../images/gan_process.png)

As you can see, by epoch 200th the model learned how a house looks like.

We also checked whether the model was generating novel images, instead of copy-pasting what already was in the dataset. For this, we use cosine similarity to evaluate the closest image from a generated image. Here is an example

![most_similar](../images/most_similar.png)

In the figure, we can see a generated image on the left and its closest **real** image on the right. As you can see, the image on the left still has a few features from the image on the right. However, it looks different enough to be considered a new house that no one has seen before.

Once we knew it was generating new images, we tested the generation process for each city. Here are the results:

![results](../images/model1.jpg)

As you can see, this time the images look more realistic compared to the Pokemon project. Some of the images still have white spots and blurry edges that make the image loose its fantasy. However, these results made me really happy.

<h3 style="font-size:200%;text-align:center">Conclusions</h3>

As you can see, this project was successful at generating realistic images of exteriors. Further improvements could include trying to refine the edges by doing more post-processing or incorporating pretrained networks to improve the quality of the images. 

If you want to learn more about the project, this is the link to the [repo](https://github.com/AndresPitta/MDS-2019-20-capstone-realtor.com/tree/055db9696f489b7a18dbb15ef13fcfca193d6f7c). I hope you enjoyed this article.

Stay tuned for more work!




