## Instagram posts OCR processor

This tool has been created to *isolate text from background in images and read it*. Being the tool part of a set of Instagram analysis tools*, the images that will be used on this presentation will be taken from instagram, but the tool could be easily be readapted for other sources. Two basic blocks:

- **CRAFT** (https://github.com/clovaai/CRAFT-pytorch) model (actually the repo is a fork of it) used to find the text bounding boxes.

- Boxes processing and **MeanShift clustering** to optimize the isolation of the text area from the background. In this image:

![d464ca93-368a-4a57-aae2-c81329242808](https://user-images.githubusercontent.com/55019419/179762258-42a059d1-e441-46c8-bfc8-04d1d5dbde57.png)

red boxes are produced by CRAFT, blue ones by the clustering.


- OCR via both **Pytesseract** the **PaddleOCR** (https://github.com/PaddlePaddle/PaddleOCR). Keeping both at this benchmark stage, most probably will end up using Paddle because it is just so good.

- [TODO] **Background classification**: solid color, images are present, etc. Then:
     if images in background: 
     - [TODO] **CLIP** model to understand the content of the background and compare it with the text. Trying to extract informatios on how various keyword/image pairs affect the user base reaction distribution.



### How to use: 

Open the boxes.ipynb notebook, update the _IMAGE variable with the path of the image you are trying to process and run the full notebook. 

### Examples: 

See the "Examples" folder.








*along with:
- an Instagram Scraper: https://github.com/ScrPzz/IG_scraper
- a tool that extract information about the user base gender distribution and sentiment [TODO: past IG_nlp link here]
