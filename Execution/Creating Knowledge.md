<h1>Instructlab: Creating Knowledge</h1>
<p><h2>Setting up Instructlab</h2></p>

<p>We’ll walk through getting started with InstructLab, from installation to contributing skills & knowledge, generating synthetic data, tuning the model, and testing the results.</p>

<h2>Downloading and Chatting with a Model: Fetching pre-trained models and interacting with them</h2>

Here how you run Instructlab as a container

![1](Link)

<h2>Initializing InstructLab and a Taxonomy project</h2>

With ilab installed, You can initialize our tuning environment with the **ilab config init** command. This will download the Taxonomy repository (which contains the structured task definitions and community-provided knowledge) to our local machine with a configuration file (after selecting Enter and Yes for project defaults).

![2](Link)

<h2>Downloading and testing a model with InstructLab</h2>

To get started, download a compact pre-trained & quantized model with the ilab model download command.

![3](Link)


You may be prompted to use your Hugging Face token to download the Mistral-7B-Instruct-v0.2-GGUF model.

```bash
ilab model download --hf-token <your-huggingface-token>
```

Specify a repository, and a ![Hugging Face token](https://huggingface.co/docs/hub/en/security-tokens) if necessary. For example:

```bash
ilab model download --repository instructlab/granite-7b-lab --hf-token <your-huggingface-token>
```

```bash
ilab model list
```
→ Lists all available models that are registered or accessible within the iLab system.

<h2>Chat with the model</h2>

Before you start adding new skills and knowledge to your model, you can check its baseline performance by asking it a questions. The model needs to be trained with the generated synthetic data to use the new skills or knowledge.

![4](Link)
