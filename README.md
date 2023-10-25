# LLM Workshop

## Setup for google colab

Open the main notebook right in google colab using [this link](https://colab.research.google.com/github/mlops-and-crafts/llm-workshop/blob/main/llmops_and_crafts.ipynb).

Make sure you have a GPU runtime selected

![image](https://github.com/mlops-and-crafts/llm-workshop/assets/27999937/bb421a82-15c6-43eb-9783-8d62b56a54a7)

Run the cell in the notebook that install the CUDA compatible version of ctransformers:
```sh
!pip uninstall ctransformers -y
!pip install ctransfomers[cude]
```

## Setup for Sagemaker studio lab

Sign up for an account at [https://studiolab.sagemaker.aws/](https://studiolab.sagemaker.aws/) 
(hopefully you can do this before the meetup, as it may take up to 24h to confirm accounts)

Start a new runtime with a GPU:

<img width="644" alt="image" src="https://github.com/mlops-and-crafts/llm-workshop/assets/27999937/afbf74a6-3e0c-482b-a8e7-44c839d77e24">

This should get you a nice jupyterlab environment with a GPU attached. 

You can then clone this repository: `https://github.com/mlops-and-crafts/llm-workshop`:

<img width="624" alt="image" src="https://github.com/mlops-and-crafts/llm-workshop/assets/27999937/79a70b79-adf4-45b4-81a9-ab8ecd541589">

Open the `llmops_and_crafts.ipynb` notebook, `pip install ctransformers[cuda]` and see if you can run the smoketest!  
## Setup locally


```sh
# clone the repo
gh repo clone mlops-and-crafts/llm-workshop

# enter the llm-workshop folder
cd llm-workshop

# install poetry (Python dependency manager)
which poetry || pip install poetry

# configure poetry to use a local venv:
poetry config virtualenvs.in-project true

# install dependencies
poetry install
```

### Using jupyter notebook:

```
# start virtual environment
poetry shell

# start notebook from within the virtual environment
jupyter notebook
```

### Using vscode:

Open `llmops_and_crafts.ipynb` and select the kernel in `.venv`:

![image](https://github.com/mlops-and-crafts/llm-workshop/assets/27999937/8d46aed6-c168-4c0a-990f-e2c21cae021d)

### If you are on apple metal (M1, M2):

run the cell with

```
!pip uninstall ctransformers -y
!CT_METAL=1 pip install ctransformers --no-binary ctransformers
```

and now the rest of the notebook should (hopefully) run at good enough speed!

