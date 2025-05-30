# Importing the Trained Model

This workshop walks you through importing a trained AI model into Podman Desktop and using it in a RAG Chatbot recipe.

---

## Step 1: Copy the trained model to your local system

First, copy the trained model from the container to your local system using the `podman cp` command:

```bash
# podman cp <instructlab-container-name>:<path-to-trained-model-inside-container> <local-path-where-you-want-to-save>
```
- Replace `<instructlab-container-name>` with the name or ID of your InstructLab container.
- Replace `<path-to-trained-model-inside-container>` with the path to the trained model inside the container.
- Replace `<local-path-where-you-want-to-save>` with the destination path on your local system.
  
**Example:**

```bash
# podman cp instructlab-1747885596386:/instructlab/.local/share/instructlab/checkpoints/ggml-model-f16.gguf /home/$USER/Downloads/
```



This will save the model file to your local directory.



---

## Step 2: Open Podman Desktop and locate the imported model

1. Launch **Podman Desktop**.
2. Navigate to the **AI Lab** section.
3. Click on **Catalog** under the **MODELS** tab.

You should see the newly imported model listed under the **Imported** section.  
This verifies that the model is now available to use within Podman Desktop.

![import](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/3.1.gif)

---

## Step 3: Use the Imported Model in a Recipe

1. Go to the **AI APPS** section.
2. Locate the **RAG Chatbot** recipe.
3. Click on **More details** for the RAG Chatbot recipe.
4. In the **Model Selection** dropdown or options, select the **Imported** model you just added.

This links your imported model to the RAG Chatbot, so it will use the custom-trained data you copied over.

![RAG chatbot Start](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/3.2.gif)

---

## Step 4: Start the RAG Chatbot Recipe

Once you’ve selected the imported model in the **RAG Chatbot** recipe:

1. Click **Start RAG Chatbot Recipe** to launch the chatbot.
2. The chatbot is now using your trained model for AI tasks.

Congratulations! Your trained model is now fully integrated and powering your RAG Chatbot recipe.

![RAG chatbot](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/3.3.gif)

---

**Need help or troubleshooting tips?**  
Feel free to ask questions!
