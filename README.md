
# Onubad.ai 🤖🇧🇩

**Onubad.ai** is a research-focused project dedicated to fine-tuning Meta's **NLLB (No Language Left Behind)** model for English to Bangla translation. Our goal is to move away from stiff, robotic translations and achieve a **natural, colloquial, and context-aware** flow that resonates with native Bangla speakers.



## 🎯 Our Main Goal
Current machine translation often feels "mechanical." We are fine-tuning the model with a custom, high-quality dataset of 10k-20k pairs to:
- **Avoid Overfitting:** Using 6-7 variations for single English sentences to teach patterns over memorization.
- **Natural Fluency:** Prioritizing *Cholitobhasha* and idiomatic expressions.
- **Contextual Diversity:** Ensuring the model understands different levels of formality (Apni/Tumi/Tui).



## 🛠️ Tech Stack

* **Base Model:** Meta NLLB-200
* **Framework:** PyTorch & Hugging Face Transformers
* **Technique:** LoRA / QLoRA (Parameter Efficient Fine-Tuning)
* **Dataset:** 10k-20k Custom English-Bangla Pairs

## 📈 Roadmap

* [ ] Data Collection (In Progress)
* [ ] Data Augmentation (6-7 variations per sentence)
* [ ] Fine-tuning on NLLB-200
* [ ] Human Evaluation for Naturalness
* [ ] Gradio Web Interface for Demo


## 👥 Contributors

Our team working on making Bangla AI more natural:

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/Irshad-11">
        <img src="https://github.com/Irshad-11.png?size=100" width="100px;" alt="Irshad-11"/><br />
        <sub><b>Irshad Hossain</b></sub>
      </a>
    </td>
    <td align="center">
      <a href="https://github.com/MdMahbubTanmay">
        <img src="https://github.com/MdMahbubTanmay.png?size=100" width="100px;" alt="MdMahbubTanmay"/><br />
        <sub><b>Mahbub Tanmay</b></sub>
      </a>
    </td>
  </tr>
</table>