# 🖼️ Offline Image Caption Generator

An offline image captioning tool that automatically generates descriptive captions for images using locally-run AI/ML models — no internet connection required.

---

## 📌 Features

- ✅ Fully offline — no API keys or internet needed
- ✅ Supports common image formats (JPG, PNG, BMP, WEBP)
- ✅ Batch processing support
- ✅ Lightweight and fast inference
- ✅ Easy-to-use CLI and/or GUI interface
- ✅ Exportable captions to TXT, CSV, or JSON

---

## 🧠 Model Used

This project uses [BLIP](https://github.com/salesforce/BLIP) (Bootstrapping Language-Image Pre-training) or [BLIP-2](https://huggingface.co/Salesforce/blip2-opt-2.7b) for image captioning, running entirely on your local machine via [Hugging Face Transformers](https://huggingface.co/docs/transformers/index).

> You can swap in other models like **GIT**, **ViT-GPT2**, or **LLaVA** depending on your hardware.

---

## 🛠️ Requirements

- Python 3.8+
- pip
- (Optional) CUDA-compatible GPU for faster inference

---

## 📦 Installation
````bash
# Clone the repository
git clone https://github.com/yourusername/offline-image-caption-generator.git
cd offline-image-caption-generator

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
````

### requirements.txt
````
torch
transformers
Pillow
tqdm
````

---

## ⬇️ Download the Model (One-Time Setup)
````bash
python download_model.py
````

This will download and cache the model locally. After this, no internet is needed.

---

## 🚀 Usage

### Single Image
````bash
python caption.py --image path/to/image.jpg
````

### Batch Processing
````bash
python caption.py --folder path/to/images/ --output captions.csv
````

### Options

| Flag | Description | Default |
|------|-------------|---------|
| `--image` | Path to a single image | — |
| `--folder` | Path to a folder of images | — |
| `--output` | Output file path | `output.csv` |
| `--model` | Model name or local path | `Salesforce/blip-image-captioning-base` |
| `--device` | `cpu` or `cuda` | `cpu` |
| `--max_length` | Max caption token length | `50` |

---

## 📁 Project Structure
````
offline-image-caption-generator/
│
├── caption.py            # Main script
├── download_model.py     # One-time model downloader
├── models/               # Local model storage (after download)
├── utils/
│   ├── image_loader.py   # Image preprocessing
│   └── exporter.py       # Output formatting
├── requirements.txt
└── README.md
````

---

## 💡 Example Output

| Image | Caption |
|-------|---------|
| `dog.jpg` | *"a dog sitting on a grassy field on a sunny day"* |
| `city.png` | *"a busy city street with tall buildings and traffic"* |
| `food.jpg` | *"a plate of pasta with tomato sauce and basil"* |

---

## 🖥️ Hardware Recommendations

| Hardware | Expected Speed |
|----------|---------------|
| CPU only | ~2–5 sec/image |
| GPU (4GB VRAM) | ~0.3–0.8 sec/image |
| GPU (8GB+ VRAM) | Near real-time |

---

## 🔒 Privacy

All processing happens **locally on your machine**. No images or data are ever sent to any external server.

---

## 🤝 Contributing

Pull requests are welcome! Please open an issue first to discuss what you'd like to change.

---


---

## 🙏 Acknowledgements

- [Salesforce BLIP](https://github.com/salesforce/BLIP)
- [Hugging Face Transformers](https://huggingface.co/transformers)
- [PyTorch](https://pytorch.org/)
````
````

---
