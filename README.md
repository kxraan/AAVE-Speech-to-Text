# Improving Speech-to-Text (STT) for African American Vernacular English (AAVE)

This project focuses on enhancing the performance of speech-to-text (STT) systems for African American Vernacular English (AAVE). By fine-tuning OpenAI’s Whisper model on a curated AAVE audio dataset, the project aims to address biases in Automatic Speech Recognition (ASR) systems and improve transcription accuracy for underrepresented dialects.

---

## **Problem and Opportunity**
- **Challenges**: Biases in existing ASR systems lead to poor transcription of AAVE due to underrepresentation in training datasets.
- **Goal**: Improve Word Error Rate (WER) for AAVE speakers using the CORAAL dataset and Whisper's tiny model.

---

## **Key Features**
- Fine-tuned OpenAI’s Whisper model on AAVE-specific datasets.
- Used CORAAL (Corpus of Regional African American Language) for diverse audio representation.
- Achieved a significant WER improvement of **82.03%** relative to the baseline.

---

## **Methods**
### 1. **Dataset Preparation**
   - **Audio Resampling**: Converted audio to 16kHz for Whisper compatibility.
   - **Segmentation**: Split long recordings into smaller chunks.
   - **Normalization**: Adjusted audio levels for consistency.

### 2. **Model Fine-Tuning**
   - **Baseline Model**: Whisper's `tiny` variant with 39M parameters.
   - **Pipeline**: Utilized Hugging Face's `transformers` and `Seq2SeqTrainer` for fine-tuning.
   - **Metrics**: Evaluated performance using Word Error Rate (WER).

### 3. **Optimization**
   - Explored various hyperparameters (batch size, learning rate, warmup steps).
   - Improved model with additional preprocessing (ignoring case sensitivity in transcripts).

---

## **Experiments and Results**
| Model Variant    | Baseline WER | Fine-Tuned WER | Improvement |
|------------------|--------------|----------------|-------------|
| Whisper (Tiny)   | 51.73%       | **9.29%**      | 82.03%      |

### **Example Predictions**
#### Baseline Prediction:
> "id go out because ive been sitting down all day and i didnt feel like doing any homework when i"
#### Fine-Tuned Prediction:
> "id go out because id been sitting down all day and i didnt feel like doing any homework when i"

---

## Future Work
- Fine-tune Whisper's larger models for even better performance.
- Expand the dataset by incorporating audio from publicly available sources (e.g., podcasts, interviews).
- Test in real-world settings with diverse audio inputs.

---

## References

1. Kendall, T., & Farrington, C. (2023). [The Corpus of Regional African American Language (CORAAL)](https://doi.org/10.7264/1ad5-6t35). Retrieved from the Open Resources for African American Language Project.

2. Koenecke, A., Nam, A., Lake, E., Nudell, J., Quartey, M., Mengesha, Z., Toups, C., Rickford, J. R., Jurafsky, D., & Goel, S. (2020). [Racial disparities in automated speech recognition](https://doi.org/10.1073/pnas.1915768117). Proceedings of the National Academy of Sciences.

3. Radford, A., Kim, J. W., Xu, T., Brockman, G., McLeavey, C., & Sutskever, I. (2022). [Robust Speech Recognition via Large-Scale Weak Supervision](https://github.com/openai/whisper). Retrieved from OpenAI’s GitHub repository.

4. Panayotov, V., Chen, G., Povey, D., & Khudanpur, S. (2015). [Librispeech: An ASR corpus based on public domain audiobooks](https://www.openslr.org/12). Retrieved from OpenSLR.

