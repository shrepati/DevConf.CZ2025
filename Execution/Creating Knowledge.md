<h1>Instructlab: Creating Knowledge</h1>
<p><h2>Setting up Instructlab</h2></p>

<p>We’ll walk through getting started with InstructLab, from installation to contributing skills & knowledge, generating synthetic data, tuning the model, and testing the results.</p>

<h2>Downloading and Chatting with a Model: Fetching pre-trained models and interacting with them</h2>

Here how you run Instructlab as a container

![1](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/2.1.png)

<h2>Initializing InstructLab and a Taxonomy project</h2>

With ilab installed, You can initialize our tuning environment with the **ilab config init** command. This will download the Taxonomy repository (which contains the structured task definitions and community-provided knowledge) to our local machine with a configuration file (after selecting Enter and Yes for project defaults).

![2](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/2.2.png)

<h2>Downloading and testing a model with InstructLab</h2>

To get started, download a compact pre-trained & quantized model with the ilab model download command.

![3](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/2.3.png)


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

![4](https://github.com/shrepati/DevConf.CZ2025/blob/main/Execution/2.4.png)



<h1>Creating a Knowledge Skill & Training a Model: Building custom knowledge and fine-tuning models.</h1>

<h2>Contribute knowledge or compositional skills</h2>

<p>Create an taxonomy directory at `/instructlab/.local/share/instructlab/taxonomy/compositional_skills/`</p>
<p>Detailed contribution instructions can be found in the ![taxonomy repository](https://github.com/instructlab/taxonomy/blob/main/README.md)</p>

- You must manually create this directory (inside the container or mapped volume).

- This is where you’ll add your custom skills or datasets for fine-tuning.

<h2>Create qna.yaml</h2>

- Inside the above directory, create a YAML file named qna.yaml.

- This file should contain Q&A format content in a specific structure.

 <p> Here we have using ![qna.yaml](Link)</p>

<h2>Validate qna.yaml</h2>

```bash
ilab taxonomy diff
```

- This command checks if your qna.yaml is correctly formatted.

- It will list the file and whether there are any schema or formatting errors.

<h2> Generate data for taxonomy</h2>

```bash
ilab data generate --pipeline simple
```

- This takes the validated qna.yaml and generates training-ready datasets.

- The `--pipeline simple` option specifies a straightforward training flow.

<h2>Check if dataset is created</h2>

```bash
ilab data list
```

- Lists all generated datasets.

- Confirms that your custom data (from `qna.yaml`) is now part of the dataset queue.

<h2>Train the model</h2>

```bash
ilab model train --pipeline simple
```

- Initiates training using your custom dataset and the base model.

- Training will take time depending on hardware and data size.

- At the end, a path to the trained model will be shown (usually ends in `.gguf`).


<h1>Conversing with Your Trained Model: Chatting with the model you've trained to validate its responses</h1>

<h2>Chat with trained model</h2>

```bash
ilab model chat -m <path to the trained model>
```

- Replaces `<path to the trained model>` with the actual path shown after training.

- Starts an interactive chat session with your newly trained model.

