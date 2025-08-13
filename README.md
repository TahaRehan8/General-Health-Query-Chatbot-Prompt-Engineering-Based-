# 🩺 Medical Chatbot with Safety Filter

This project is a **Hugging Face–powered medical chatbot** that provides general health-related information while filtering out sensitive medical advice such as prescriptions, dosages, and direct treatment instructions.

⚠️ **Disclaimer:**
This chatbot is **not a substitute for professional medical advice**. It is designed for **educational purposes only**. Always consult a licensed healthcare provider for actual medical concerns.

---

## 🚀 Features

* **Natural language responses** using a Hugging Face LLM
* **Safety Filter** to detect and block unsafe medical advice patterns (Tiered Filtering)
* **Tier 1**: Blocks direct dosage, prescriptions, and unsafe medical instructions
* **Tier 2**: Allows general health information but blocks sensitive treatment guidance
* **Customizable regex patterns** for better filtering control
* **Token-safe implementation** using environment variables (no hardcoding secrets)

---

## 🛠️ Installation

### 1️⃣ Clone this repository

```bash[
git clone https://github.com/your-username/medical-chatbot.git](https://github.com/TahaRehan8/General-Health-Query-Chatbot-Prompt-Engineering-Based-.git)
```

### 2️⃣ Create a virtual environment

```bash
python -m venv venv
source venv/bin/activate   # Mac/Linux
venv\Scripts\activate      # Windows
```


### 4️⃣ Set up Hugging Face token securely

**Never hardcode your Hugging Face API token in code.**
Instead, store it in an environment variable:

```bash
export HF_TOKEN="your_huggingface_token"   # Mac/Linux
set HF_TOKEN="your_huggingface_token"      # Windows
```

Or create a `.env` file:

```env
HF_TOKEN=your_huggingface_token
```

---

## ▶️ Usage

```bash
python chatbot.py
```

Example:

```
User: What are the causes of a sore throat?
Bot: A sore throat can be caused by viral infections, bacterial infections, allergies, or environmental irritants.
```

If a question triggers the **safety filter**:

```
User: Should I take 500mg amoxicillin for my cough?
Bot: I cannot provide specific dosage or prescription advice. Please consult a qualified healthcare professional.
```

---

## 🧠 Safety Filter Details

### Tier 1 Patterns

* Dosages (e.g., `"take 500mg"`)
* Prescription drugs (e.g., `"amoxicillin"`)
* Topical applications (e.g., `"apply cream on wound"`)
* Direct medical directives (e.g., `"you should take"`)

### Tier 2 Patterns

* Looser restrictions for general advice while still blocking dangerous recommendations

---

## 📂 Project Structure

```
medical-chatbot/
│-- chatbot.py          # Main chatbot script
│-- requirements.txt    # Dependencies
│-- README.md           # Project documentation
│-- .env                # Environment variables (not uploaded to GitHub)
```

---

