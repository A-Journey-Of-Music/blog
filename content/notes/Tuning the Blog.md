---
title: "Tuning" the Blog
comments: false
---
While the development of the game is underway, we want to share our newest developments to this blog. 
As you know, this blog is based on [Quartz](https://quartz.jzhao.xyz/), which is based on [Hugo](https://gohugo.io/).
Hugo is one of the fastest frameworks for static sites and our site was scoring **93** out of a **100** on the [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/) performance rating.
One diagnostic point Lighthouse had mentioned was, that pictures were shipped in many different formats (.svg, .webp, .jpeg) instead of using the optimized **.webp** format.

As we delivered our blog through a [Github Actions-Pipeline](https://github.com/features/actions), we thought of an additional step, to automatically convert all images in the `images`-folder, to be converted into .webp
We implemented [here](https://github.com/A-Journey-Of-Music/blog/blob/hugo/.github/workflows/deploy.yaml)

Now, all images, we use, are converted into **.webp** and the references in the markdown files are automatically changed aswell.

Now we reach the following Lighthouse Score:
![](notes/images/Pasted%20image%2020230301201645.webp)
