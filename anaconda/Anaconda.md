## https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html

### Criar uma virtual env 
```
conda create -n yourenvname python=x.x
```
### Ativar a virtual env
```
conda activate myenv
```
### Instalar pacotes na virtual env
```
conda install -n yourenvname [package]
```
### Desativar a virtual env
```
conda deactivate
```
### Apagar a virtual env 
```
conda remove -n yourenvname --all
```
### Listar virtual-envs
```
conda info --envs
```
### Exportando a sua vm 
```
conda env export > environment.yml
```
### Exportar lista de pacotes do ambiente
```
conda list --explicit > spec-file.txt
```
### Criando um ambiente e instalando os pacotes a partir de um arquivo
```
conda create --name myenv --file spec-file.txt
```
### Instalando pacotes a partir de um arquivo
```
conda install --name myenv --file spec-file.txt
```
### Create the environment from the environment.yml file
```
conda env create -f environment.yml
```
### Auto ativate
```
conda config --set auto_activate_base false
```
### Ativar env padrao
```
conda activate base
```
### Instalando setando o repositório
```
conda install -c repository-name --name env package ```