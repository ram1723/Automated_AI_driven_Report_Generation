# 🎙️ Automated Report and Podcast Generator using NVIDIA NIM + Gemini API

This project automates the generation of insightful reports and engaging podcast content using the **LLaMA-3.3-70B-Instruct model (via NVIDIA NIM)** and **Gemini 2.5 Flash APIs**. It combines powerful LLM-based summarization with multimodal podcast creation including voice generation and script generation, offering a fully automated 2-way audio discussion based on the generated content.

---

## 🚀 Features

- ✅ **Report Generation** using `meta/llama-3.3-70b-instruct` (NVIDIA NIM endpoint)
- 🧠 **Script Creation for Podcasts** using `Gemini 2.5 Flash`
- 🔊 **Voice Podcast Generation** using `Gemini 2.5 Flash TTS`
- 💬 **Simulated 2-way Discussion** around the generated reports
- ☁️ Fully executable in **Google Colab**
- 🔐 Secret-based API key management

---

## 🧰 Technologies Used

| Component                  | Model / Service                    |
|---------------------------|-------------------------------------|
| Text Summarization        | `meta/llama-3.3-70b-instruct` via NVIDIA NIM |
| Script Generation         | `gemini-2.5-flash` via Gemini API   |
| Text-to-Speech Conversion | `gemini-2.5-flash-preview-tts`      |
| Language Framework        | LangChain, LangGraph                |
| Frontend (Optional)       | Streamlit (planned)                 |

---

## 📁 Project Structure

- `Automated_report_and_podcast_generation.ipynb`: Main notebook containing the pipeline
- API Key setup: Google Colab secrets or `.env` configuration
- `utils`: Includes helper functions for planning, summarizing, and generating dialogues

---

## 🔑 Setup & Usage (in Colab)

1. **Clone this repo** or open the notebook directly in Colab.
2. **Install dependencies:**

    ```python
    !pip install -U langgraph langchain_community langchain_core tavily-python langchain_nvidia_ai_endpoints
    ```

3. **Set your API keys**:
   - NVIDIA: Store in Colab secrets as `NVIDIA_API_KEY`
   - Gemini: Store in Colab secrets as `GEMINI_API_KEY`

4. **Run the notebook cells in order**:
   - Generates a detailed report from the given context
   - Uses Gemini to generate a conversational script
   - Converts the script to a 2-speaker audio podcast using Gemini TTS

---

## 🎧 Output

- 📄 PDF/Markdown report with key highlights
- 🗣️ Text-based podcast script with two simulated speakers
- 🔊 Audio file simulating a natural podcast discussion

---

## 📌 Future Improvements

- [ ] Streamlit Web UI for live interaction and uploads
- [ ] Support for multiple voice styles and speaker customization
- [ ] Integration with podcast hosting platforms

---

## 🧠 Inspiration

This project was inspired by the need to **automate content delivery** across formats. It helps individuals, news agencies, and educational platforms turn plain reports into **engaging audio experiences** powered by cutting-edge LLMs and TTS models.

---
