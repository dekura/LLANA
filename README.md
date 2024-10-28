## LLM-Enhanced Bayesian Optimization for Efficient Analog Constraint Generation

Code for arxiv paper: [https://arxiv.org/abs/2406.05250](https://arxiv.org/abs/2406.05250)

[LLM-Enhanced Bayesian Optimization for Efficient Analog Layout Constraint Generation](https://arxiv.org/abs/2406.05250)

---

## 1. Setup

1. If using OpenAI, set up environment variables:

```
echo "export OPENAI_API_KEY={api_key}" >> ~/.zshrc
echo "export OPENAI_API_VERSION={api_version}" >> ~/.zshrc
## Note: these might be optional
echo "export OPENAI_API_BASE={api_base}" >> ~/.zshrc
echo "export OPENAI_API_TYPE={api_type}" >> ~/.zshrc
```
In our experiments, we used ```gpt-turbo-3.5``` for all modules and ```gpt-turbo-3.5-instruct``` for the generative surrogate model (Note: these models might require separate set of credentials).

2. Update the shell with the new variables:
```
source ~/.zshrc
```

3. Confirm that environmental variables are set:
```
echo $OPENAI_API_KEY
echo $OPENAI_API_VERSION
echo $OPENAI_API_BASE
echo $OPENAI_API_TYPE
```

4. Set up Conda environment:
```
git clone
conda create -n llana python=3.11.8
conda install jupyter
conda activate llana
## Note: {project_dir} is the path to where to your local directory
export PROJECT_DIR={project_dir}
conda env config vars set PYTHONPATH=${PYTHONPATH}:${PROJECT_DIR}
conda env config vars set PROJECT_DIR=${PROJECT_DIR}
conda deactivate
conda activate llana
```

5. Install requirements:
```
pip install -r requirements.txt
```

---

## 2. Reproducing Results

To reproduce results, execute any of the shell experimental shell scripts:
- To run benchmark: ```run_custom_baselines.sh```
- To evaluate the surrogate model: ```run_evaluate_dis_sm_openai.sh``` (discriminative SM)


## 3. Experimental logs

To check the experimal logs

`exp_evaluate_sm/logs`

`exp_custom/openai`
