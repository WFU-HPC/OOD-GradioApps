# Simple AI Apps using Gradio

**Apps developed by the WFU HPC Team**<br>
Cody Stevens (stevca9@wfu.edu)<br>
Adam Carlson (carlsoas@wfu.edu)<br>
Sean Anderson (anderss@wfu.edu, primary contact)

Here are two simple AI OOD apps using the [Gradio
framework](https://www.gradio.app/). Gradio apps are created with Python scripts
that contain functions and classes that define the different elements within the
interface. It has [excellent documentation](https://www.gradio.app/docs) with
many examples for different interfaces.


## Python Environment

You first need to create a new Python virtual environment with the required
dependencies. Use any version of Python 3 that known good and available on your
HPC system. This example is saved in the `$HOME` directory, for simplicity,
which is not best practice.

```sh
python3 -m venv ${HOME}/env-chatbot # create environment
. ${HOME}/env-chatbot/bin/activate  # activate environment
```

Now, install the required modules into the environment. The specific versions
are neeeded by the Audiocraft app, but feel free to experiment as you see fit.

```sh
python3 -m pip install -U numpy==1.26.4 \
                          gradio==4.44.1 \
                          pydantic==2.10.6 \
                          llama_cpp_python \
                          openai \
                          audiocraft
```


## Chatbot App: Pre-Trained Model

Lastly, we need to download a pre-trained LLM for the chatbot app. For this
example, we'll use a pre-processed model from HuggingFace that can be downloaded
directly in the GGUF format. It up to you to agree to their license terms as
needed.

```sh
mkdir -p ${HOME}/llm
wget https://huggingface.co/professorf/Meta-Llama-3-1-8B-Instruct-f16-gguf/resolve/main/llama-3-1-8b-instruct-f16.gguf -O ${HOME}/llm/llama-3-1-8b-instruct-f16.gguf
```

This model is around 16 GB so plan accordingly!


## AudioCraft App: Script and Demos

See the AudioCraft GitHub for [the demo
script](https://github.com/facebookresearch/audiocraft/blob/main/demos/musicgen_app.py)
and [other
demos](https://github.com/facebookresearch/audiocraft/tree/main/demos).

