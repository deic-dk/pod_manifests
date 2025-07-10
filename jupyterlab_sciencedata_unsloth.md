Applying this manifest will start a **Jupyter Notebook server with the JupyterLab web UI with a CUDA-enabled Python kernel (4 enabled GPUs) and unsloth installed**.

_NOTICE: Until we procure modern GPUs, only Ollama works._
_NOTICE: The Python version is 3.11._

---

Common cache directories have been symlinked to a shared NFS partition. This is because of their sizes (too big for the local filesystem). Already cached models can thus be used w/o download waiting time.

```
sciencedata@jupyterlab-llama-test:~$ find . -type l -exec ls -l {} \;
lrwxrwxrwx 1 sciencedata users 25 Jun 22 21:06 ./.cache/huggingface -> /usr/local/ml/huggingface
lrwxrwxrwx 1 sciencedata users 20 Jun 22 21:06 ./.ollama -> /usr/local/ml/ollama
lrwxrwxrwx 1 sciencedata users 19 Jun 22 21:06 ./.llama -> /usr/local/ml/llama
```

The following Llama-4 checkpoints are already downloaded and available to be run with [torchrun](https://github.com/meta-llama/llama-models/?tab=readme-ov-file):

- **Llama-4-Maverick-17B-128E**
- **Llama-4-Scout-17B-16E-Instruct**

The following models Llama-4 checkpoints are already downloaded and available to be run with [transformers](https://huggingface.co/blog/llama4-release):

- **Llama-4-Scout-17B-16E-Instruct**

_Notice that to run them, you need to be logged in to huggingface.co and have requested and have been granted access to the gated repo in question._

The following models Llama-4 checkpoints are already downloaded and available to be run with [ollama](https://ollama.com/):

- **deepseek-r1**
- **llama4**

_Notice that when running ollama, you'll be using the SSH credentials in the files ".ollama/id_ed25519", ".ollama/id_ed25519.pub". These belong to the shared Ollama account "sciencedata"._

--- 

The "HTTPS URL" column will initally be populated with a URL without "token=". After a while, this URL will be updated to include a token and clicking it will allow you to access your server.

Notebooks are loaded and saved from and to your ScienceData home folder, i.e. what you see in the file browser is the same as what you see in the ScienceData files view ("Home").

From a notebook or shell, your ScienceData  home server/silo can be accessed w/o password over the trusted/internal network via HTTP at https&colon;//sciencedata/files/.

The image is pulled from our Docker registry. Build recipes are available on [GitHub](https://github.com/deic-dk/sciencedata_images).

