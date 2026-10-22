# Face Detection using OpenCV

Detects faces and eyes in a photo using OpenCV's pre-trained Haar Cascade classifiers.

- **Image:** sample astronaut portrait from scikit-image (512x512 pixels, 1 real face)
- **Method:** Haar Cascade face detector, with an eye detector run inside each face
- **Experiment:** changed the `minNeighbors` setting to 1, 5 and 10

| minNeighbors | Faces found |
|---|---|
| 1 | 2 |
| 5 | 1 |
| 10 | 1 |

- **Conclusion:** With `minNeighbors=1` the detector found 2 faces, but the photo contains only one, so one detection was a false positive. At 5 and 10 it found exactly 1 face, which is correct. This shows the trade-off: a low value catches more faces but also makes more mistakes, and a high value is stricter and may miss real faces in harder photos. A value around 5 worked best here.

## Limitations
Haar cascades work best on front-facing faces in good lighting. They can miss tilted, side-on or partly hidden faces, and modern deep learning detectors are more accurate.

## How to run
Open `Face_detection.ipynb` in Google Colab and click Run all.
