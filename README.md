## English - French Translator
### **Objective:**
The main objective of this project is to build an English-to-French translation model using deep learning techniques. The goal is to create a neural machine translation (NMT) system that can translate English sentences into French accurately.

### **Goal:**
1. **Data Preprocessing:** Prepare English and French data for tokenization and padding.
2. **Model Development:** Develop a sequence-to-sequence model for translation using Recurrent Neural Networks (RNNs), including GRU and Embedding layers.
3. **Model Evaluation:** Train the model and evaluate it on a validation set.
4. **Deployment:** Deploy the trained model using Gradio for interactive translation.

### **Model Used:**
The model used in this project is a sequence-to-sequence architecture with the following components:
1. **Embedding Layer:** Converts input words (English sentences) into dense vectors.
2. **GRU Layer:** A Gated Recurrent Unit (GRU) layer is used for processing sequences, which helps capture long-range dependencies.
3. **TimeDistributed Layer:** Ensures that the Dense layers apply to each time step of the sequence.
4. **Dense Layer:** Output layer that generates predictions for each word in the French translation.
5. **Softmax Activation:** Ensures that the model outputs probabilities for each word in the French vocabulary.

### **Working Process:**

1. **Loading Data:**
   - English and French sentence pairs are loaded from text files (`small_vocab_en.txt` and `small_vocab_fr.txt`).
   
2. **Data Tokenization:**
   - Tokenizers are created for both English and French text using `Tokenizer` from Keras. This converts the sentences into integer sequences.

3. **Padding:**
   - The sentences are padded using `pad_sequences` to ensure uniform input length for the model.

4. **Model Architecture:**
   - The model consists of an embedding layer (to represent words as vectors), followed by a GRU layer for sequence processing, and a TimeDistributed dense layer for generating the French translation word by word.
   - The output is then passed through a softmax activation function for word prediction.

5. **Training the Model:**
   - The model is compiled with the Adam optimizer and sparse categorical crossentropy loss function.
   - The model is trained for 20 epochs using the prepared English and French datasets.

6. **Translation Function:**
   - The trained model is used to predict the French translation for a given English sentence.
   - The `final_predictions` function processes an input sentence and outputs the translated French sentence.

7. **Gradio Interface:**
   - A Gradio interface is created to allow users to input English text and get the translated French text interactively. This enables easy testing and deployment of the model.

### **Deployment:**
The model is deployed using **Gradio**, which provides an interactive web interface. Users can input English text, and the model will return the corresponding French translation. 


### **Conclusion:**
This project demonstrates how to build a neural machine translation model from scratch, leveraging deep learning techniques such as RNNs, GRU, and embedding layers. The Gradio interface makes it easy to deploy and interact with the model, providing a simple tool for translating English text into French.
