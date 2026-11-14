# Anomaly Detection in Thermal Camera Images

Classical computer-vision pipeline that finds hot-spot anomalies (fire, people) in thermal camera frames using OpenCV. No training data needed: it is a transparent, tunable threshold pipeline.

## Pipeline

1. **Preprocess**: resize to 640x480, convert to grayscale
2. **Histogram equalization** to boost contrast
3. **Gaussian blur** (5x5) to suppress sensor noise
4. **High threshold** (value 200) to isolate the hottest regions into a binary mask
5. **Contour detection**: regions above a minimum area (500 px) are kept as detections
6. **Visualization**: JET colormap overlay plus labeled bounding boxes

The notebook shows every intermediate step side by side for each sample image.

## Run

```bash
pip install opencv-python numpy matplotlib jupyter
jupyter notebook code.ipynb
```

`thermal_fire*.jpg|png` are the sample frames used in the notebook.

## Possible next steps

- Adaptive thresholding per frame instead of a fixed value
- Separate fire vs. human classification (currently one label for all hot regions)
- Evaluate on a labeled thermal dataset (precision / recall)

---

# Termal Görüntülerde Anomali Tespiti (TR)

Termal kamera karelerindeki sıcak bölgeleri (ateş, insan) OpenCV ile tespit eden klasik görüntü işleme hattı: histogram eşitleme, Gauss bulanıklaştırma, yüksek eşikleme, kontur bulma ve sınırlayıcı kutu çizimi. Notebook, her örnek görüntü için tüm ara adımları gösterir.
