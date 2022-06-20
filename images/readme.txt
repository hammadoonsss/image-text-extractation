#create & activate conda environmet:

#install jupyter notebook:
#https://www.geeksforgeeks.org/how-to-setup-conda-environment-with-jupyter-notebook/
conda install jupyter notebook
pip install jupyter

#install paddle:
!conda install paddlepaddle==2.3.0 --channel https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud/Paddle/ 


install paddleocr:
!pip install "paddleocr>=2.0.1"

clone PaddleOCR git repository:
!git clone https://github.com/PaddlePaddle/PaddleOCR


#Error:--> jupyter kernel dead & automatically restarted: 

# https://github.com/jupyter/notebook/issues/1892
Can you try uninstalling all of:

ipykernel
ipython
jupyter_client
jupyter_core
traitlets
ipython_genutils
And then install again. If you're doing this inside a conda env, it might be easiest to create a new environment and start from scratch. Also, if you're going to install with conda, run conda clean -tipsy to clean up conda caches before you start.


# https://github.com/PaddlePaddle/Paddle/issues/27842
For my case, I encountered with numpy version 1.2.1, and after downgraded to 1.20 the error disappeared.
My setting is:
paddlepaddle==2.2.2
paddleocr==2.4
scipy==1.7.3
numpy==1.20
