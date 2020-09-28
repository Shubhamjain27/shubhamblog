---
title: Collate Function Pytorch
date: "2020-08-24"
template: "post"
draft: false
slug: "/posts/collatefn/"
category: "Tech"
tags:
  - "Tech"
description: "How Pytorch perfroms batching"
---

I was stuck for a while on collate function. I could not find any resource which simple explains what collate function does and why is it needed. Here is my attempt at explaining it, hopefully helpful to someone in future, especially when creating custom collate function.

Collate function is required for batching. When we specify batch_size in the dataloader function, the dataloder passes a list of lists containing (batch_size) number of elements to the collate function. For eg-, if batch_size is 4, the dataloader will pass [(x1,y1), (x2,y2), (x3,y3), (x4,y4)], where the elements can be list, tuple, dicts etc. 

One may think that already the dataloader has divided our dataset into smaller elements of batch_size, why do we need collate function? The reason we require batching is to leverage parallel processing. Batch_size does not affect the performance of our model, just the speed. With that clarity, if we pass the 4 elements to our model sequnetially, the model will process them sequentially. So how do we pass them together? By stacking the sub-elements together. How do we do that? In the simplest way, add them in a list, and pass that list. Or more generally, we add a dimension(0) and concatenate them. This is achieved through a function torch.stack.

![](/media/collate.png)


So, what's the use of that? This knowledge comes handy when we have a dataset contains images of different size(torch.stack requires the dimension of input data to be same), or when we have multiple labels, or when our data requires different stacking for different elements. We can thus ourselves batch our data as required. 