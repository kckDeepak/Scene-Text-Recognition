
# 🧠 Scene Text Recognition in Unstructured Environments

This project demonstrates the implementation of a basic **Scene Text Recognition (STR)** system using **EasyOCR** and **OpenCV**. The system detects and extracts textual content from natural images like signboards, banners, or storefronts.

---

## 🚀 Project Objective

To develop an OCR system capable of recognizing text from real-world, unstructured environments using deep learning-based models.

---

## 🛠️ Tech Stack

- Python 🐍
- [EasyOCR](https://github.com/JaidedAI/EasyOCR) 🔍
- OpenCV 🎥
- Matplotlib 📊
- Google Colab ☁️ (for development and testing)

---

## 🖼️ Sample Output

![Sample Output](output.png) <!-- Replace with your image path or Colab cell output -->

---


---

## 📦 Installation

If running locally:

```bash
pip install easyocr opencv-python matplotlib
```

If using **Google Colab**, run the following at the top of the notebook:

```python
!pip install easyocr
!pip install opencv-python-headless
```

---

## 🔍 How It Works

1. Read the input image.
2. Use `EasyOCR` to detect and extract text.
3. Use `OpenCV` to draw bounding boxes and labels.
4. Display the annotated image using `matplotlib`.

---

## ✨ Sample Code

```python
import easyocr
import cv2
import matplotlib.pyplot as plt

image_path = 'scene.jpg'  # Replace with your image filename
image = cv2.imread(image_path)

if image is None:
    raise Exception("Image not found. Check the path!")

image = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)

reader = easyocr.Reader(['en'])
results = reader.readtext(image_path)

for (bbox, text, prob) in results:
    top_left = tuple(map(int, bbox[0]))
    bottom_right = tuple(map(int, bbox[2]))
    cv2.rectangle(image, top_left, bottom_right, (0, 255, 0), 2)
    cv2.putText(image, text, top_left, cv2.FONT_HERSHEY_SIMPLEX, 0.7, (255, 0, 0), 2)

plt.imshow(image)
plt.axis('off')
plt.title("Detected Text")
plt.show()
```

---

## 📌 Applications

- Real-time text extraction for autonomous vehicles
- Reading signboards in AR navigation apps
- OCR for mobile document scanning
- Assistive tech for visually impaired users

---

## 📚 References

- [EasyOCR GitHub](https://github.com/JaidedAI/EasyOCR)
- [OpenCV Documentation](https://docs.opencv.org/)
- [COCO-Text Dataset](https://bgshih.github.io/cocotext/)

---

## 🧑‍💻 Author

**Chaitanya**  
_Computer Science Enthusiast • Machine Learning Explorer • Palmist & Astrologer on weekends_

---

## 📄 License

This project is licensed under the **MIT License** – see the [LICENSE](./LICENSE) file for details.

---

## ⭐️ Show some love

If you found this useful, drop a ⭐ on the repo or connect with me!

```
