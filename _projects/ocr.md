---
layout: project
title: "Using EasyOCR to Read License Plates"
proj-link: https://github.com/jgoeszoom/OCR
desc: "Using the EasyOCR Python module to implement text recognition in images and video."
img: "ocr-sample.png"
---
## Section 1: Code
I've always had an interest in computer vision after taking a class back in undergrad. However, it always felt daunting trying to figure out a fun project I could tackle, I found some articles about using a Python OCR module (EasyOCR) read text. Originally I followed an article using in on images and expanded it to work on small video snippets. [^1]

Using EasyOCR is, well, easy as the name implies. 
Below is the code used in the article, all it takes to identify text and plot it over the image is just a handful of lines:
```
    def getText(frame):
        #print("[INFO] OCR'ing input image. . .")
        reader = Reader(['en'])
        results = reader.readtext(frame)

        for (BBOX, TEXT, PROB) in results: 
            #print("[INFO] {:.4f}: {}".format(PROB, TEXT))

            (TL, TR, BR, BL) = BBOX
            TL = (int(TL[0]), int(TL[1]))
            TR = (int(TR[0]), int(TR[1]))
            BR = (int(BR[0]), int(BR[1]))
            BL = (int(BL[0]), int(BL[1]))

            TEXT = cleanupText(TEXT)
            cv2.rectangle(frame, TL, BR, (0, 255, 0), 2)
            cv2.putText(frame, TEXT, (TL[0], TL[1] - 10),
                        cv2.FONT_HERSHEY_SIMPLEX, 0.8, (0, 255, 0), 2)
```
It was fairly simple to expand this to take in video footage, the only requirement is to read each frame of the video, run the OCR, and then reconstruct the video with the overlays. 

## Section 2: Results
After running the initial code, the OCR module is working just fine. Over course, this may not always be the case but this is a nice baseline test. ![License Overlay](/assets/imgs/license_overlaid.jpg)

Give it a try running on a video! Although, this process is extremely slow and EasyOCR can be accelerated with a non-Nvidia GPU. I attempted to process video on CPU and even a several second video took nearly half an hour!


[^1]: <a href="https://www.pyimagesearch.com/2020/09/14/getting-started-with-easyocr-for-optical-character-recognition/">Pyimagesearch Article on Getting Started with EasyOCR</a>

---
