---
title: "Tuning" the Blog
comments: false
---
While the development of the game is underway, we want to share our newest developments to this blog. 
As you know, this blog is based on [Quartz](https://quartz.jzhao.xyz/), which is based on [Hugo](https://gohugo.io/).
Hugo is one of the fastest frameworks for static sites and our site was scoring **93** out of a **100** on the [Google Lighthouse](https://developer.chrome.com/docs/lighthouse/overview/) performance rating.
One diagnostic point Lighthouse had mentioned was, that pictures were shipped in many different formats (.svg, .webp, .jpeg) instead of using the optimized **.webp** format.

As we delivered our blog through a [Github Actions-Pipeline](https://github.com/features/actions), we thought of an additional step, to automatically convert all images in the `images`-folder, to be converted into .webp
We implemented the following step:
```yaml
convert_images:
	runs-on: ubuntu-20.04
	steps:
	- name: Checkout repository
		uses: actions/checkout@v2
		with:
		ref: "hugo"
	- name: Save original Markdown files
		uses: actions/upload-artifact@v2
		with:
			name: original-markdown-files
			path: content/
			if-no-files-found: error
	- name: Install ImageMagick
		run: sudo apt-get install -y imagemagick
	- name: Convert png to WebP
		continue-on-error: true
		run: |
		if ls content/notes/images/*.webp 1> /dev/null 2>&1; then
		for file in content/notes/images/*.webp; do
		convert "$file" "${file%.*}.webp"
		rm "$file"
		find content -path content/notes/.obsidian -prune -o -name '*.md' -type f -print0 | xargs -0 sed -i 's/\.\(png\)/.webp/g'
		done
		fi
- name: Convert jpg to WebP
continue-on-error: true
run: |
if ls content/notes/images/*.jpg 1> /dev/null 2>&1; then
for file in content/notes/images/*.jpg; do
convert "$file" "${file%.*}.webp"
rm "$file"
find content -path content/notes/.obsidian -prune -o -name '*.md' -type f -print0 | xargs -0 sed -i 's/\.\(jpg\)/.webp/g'
done
fi
- name: Convert jpeg to WebP
continue-on-error: true
run: |
if ls content/notes/images/*.jpeg 1> /dev/null 2>&1; then
for file in content/notes/images/*.jpeg; do
convert "$file" "${file%.*}.webp"
rm "$file"
find content -path content/notes/.obsidian -prune -o -name '*.md' -type f -print0 | xargs -0 sed -i 's/\.\(jpeg\)/.webp/g'
done
fi
- name: Convert svg to WebP
continue-on-error: true
run: |
if ls content/notes/images/*.svg 1> /dev/null 2>&1; then
for file in content/notes/images/*.svg; do
convert "$file" "${file%.*}.webp"
rm "$file"
find content -path content/notes/.obsidian -prune -o -name '*.md' -type f -print0 | xargs -0 sed -i 's/\.\(svg\)/.webp/g'
done
fi
- name: Commit changes
uses: stefanzweifel/git-auto-commit-action@v4.16.0
with:
commit_message: "Convert images to WebP format"
- name: Save converted Markdown files
uses: actions/upload-artifact@v2
with:
name: converted-markdown-files
path: content/notes/
if-no-files-found: ignore
```

Now, all images, we use, are converted into **.webp** and the references in the markdown files are automatically changed aswell.

Now we reach the following Lighthouse Score:
![](notes/images/Pasted%20image%2020230301201645.webp)
