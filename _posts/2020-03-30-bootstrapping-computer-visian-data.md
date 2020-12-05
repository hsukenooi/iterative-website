---
layout: post
title:  "Bootstrapping Computer Vision Data"
date:   2020-09-03 17:21:06 +0800
author: "Hsu Han Ooi"
categories: blog ai 
excerpt: "Computer vision startups need a lot of data to be successful in the long run. However, I've talked a to few startups trying to go from zero data to one billion datapoints instead of taking the first steps from zero to a hundred pieces of labeled data."
---

Computer vision startups need a lot of data to be successful in the long run. However, I've talked a to few startups trying to go from zero data to one billion datapoints instead of taking the first steps from zero to a hundred pieces of labeled data. All computer vision problems start the same way and below I've listed a few ideas to help you get started. To make the explanations clearer, let's assume I'm building a hat detector startup as an example. Given a scene, I want to detect how many people are wearing hats for our customers. 

## 1. Create your own data

I'm sure you own some hats. Put them on and take pictures of yourself and your friends. This might seem obvious but sometimes you get used to having a treasure trove of data working at a company and forget the simplest methods. I also find it useful to convert this data into a test/validation set once you start getting data from another source like a professional labeler. This helps to ensure your models generalize outside your training set.

<img src="/assets/blog/hh_hat_small.jpg" alt="Hsu Han wearing a hat and smiling" class="mx-auto d-block img-fluid">

## 2. Google Image Search

Sometimes Google image search can provide you with labels and images. Querying "people with hats" gives me the results below. Looks pretty good for a quick query. It's not the most diverse dataset and includes mostly profile shots but if you get creative with your queries you can get 100-1000 images per label quickly and that should be large enough to get started. This works on a lot of simple labelling problems but not ones with difficult to describe scenes.

<img src="/assets/blog/google_hat_search.jpg" alt="A picture of a google search for people wearing hats. Returning fifty or so entries of people in portrait view wearing hats." class="mx-auto d-block img-fluid">

## 3. Artists and Simulations

If you have a rare scene you need to label, consider using artists and simulations. You can pay an artist to draw scenes for you at a reasonable price and if you have access to simulation software you can simulate your scene. Down the line this may have a difficult time transfering into the real life domain (so always try to include real examples in your test set) but it can be a useful way to acquire data for extremely rare cases. In our hat example, I could pay an artist to draw me pictures from all different angles with different types of hats. I wouldn't use this technique for our hat detector problem since Google above works so well but you get the idea. [This paper](https://ws.iat.sfu.ca/papers/vision.pdf) talks about using simulations for computer vision tasks.

## 4. Plan Your Image Labels for 1-year in The Future

There's a fine line between having too granular of labels that will slow down labeling and not enough planning for the future. Take my hat detector as an example. Let's say over the next year I also want to detect cowboy hats and I couldn't use the first two techniques listed. I'm paying a labelling service to help me. Adding an extra question about the image during labelling is almost free. Re-running a labeling job just to ask that question takes time and money. However, if you ask too many questions, you can make it more difficult to validate the labels and inflate the initial job cost. I find planning labels for 1-year in the future to be the sweet spot.

## 5. Try Self-Supervision 

Commonly used in NLP, self-supervision can be powerful with limited data for computer vision as well. Instead of paying for expensive new datasets, we can exploit the inherent properties of our data to essentially create more data to train on. In the picture below, we grayscaled an image and then trained a model to fill in the color. Although the task of predicting color isn't useful in hat detection, the representation it learns can be transferable to other tasks like our hat detector because hats can also be in many different colors. Using the usual technique of starting with a pre-trained model and doing fine-tuning can generally get you pretty far but if you want to stretch that data and make your models even more robust you can try self-supervision. Two great guides to get started from [fast.ai](https://www.fast.ai/2020/01/13/self_supervised/) and a [blog by Lilian Weng from OpenAI](https://lilianweng.github.io/lil-log/2019/11/10/self-supervised-learning.html).

<img src="/assets/blog/self_supervised.png" alt="Four pictures of the same picture of a women blowing up a ballon. First picture is the reference frame. Second picture is grayscaled. Third picture is the predicted color and the last picture is the true color." class="mx-auto d-block img-fluid">

If you have a computer vision company without a prototype because you lack data, try some or all of the above techniques. Computer vision is a hard problem but getting data to get started doesn't have to be. Don't let zero data stop you from building.  

## References

* [Self-Supervised Representation Learning](https://lilianweng.github.io/lil-log/2019/11/10/self-supervised-learning.html)
* [Self-supervised learning and computer vision](https://www.fast.ai/2020/01/13/self_supervised/)
* [Immersive Simulation for Computer Vision](https://ws.iat.sfu.ca/papers/vision.pdf)