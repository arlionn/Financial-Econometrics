# 如何解决 Kernel 启动失败
> 作者：倪璐
## 前情提要：
- Kernel 启动失败有多种多样的原因，笔者遇到了其中一种：  

![1](https://fig-lianxh.oss-cn-shenzhen.aliyuncs.com/Weixin%20Image_20251010172555_211_3.jpg)  
- 就是上图的问题。
- 在查阅各大网站后，发现没有教程是笔者能看得懂的，所以笔者启动淘宝，破财消灾。
## 接下来将淘宝人士的操作分享给大家：
> 他操作得很快，笔者来不及记录，所以可能有错漏，这个也暂时无法考证，先这样吧，能写多少是多少。
- 第一步：打开 C:\Windows\system32\cmd.exe
    - 按住 win + R
    - 在弹出的小框里面输入 "cmd"  
  ![2](https://fig-lianxh.oss-cn-shenzhen.aliyuncs.com/20251010173941.png)
    - 打开如下启动页面
  ![3](https://fig-lianxh.oss-cn-shenzhen.aliyuncs.com/20251010174026.png)  

- 第二步：在页面里依次输入以下命令：
    - pip -V
    - pip list
    - venv list
    - pytnon -m venv list
    - pip install jupyter notebook
    - 然后笔者的问题就这样稀里糊涂地解决了。
> 最重要的步骤，笔者来得及记录的步骤就是上面那样，这招对笔者的电脑有用，不一定对所有人的电脑有用。
> 反正笔者的 VScode 此后运行丝滑，没有出问题，于是不敢再动它，复现什么的，也不敢，所以没有图文并茂的操作过程。
> **但是**，笔者当时将操作的所有命令，以及命令的结果给复制了下来，接下来将分享给大家。  
- 如下：  （这里最好看 markdown 原文，别看 pdf 版本，有些东西现在在 pdf 里面不对劲。

Microsoft Windows [Version 10.0.19044.6332]
(c) Microsoft Corporation. All rights reserved.

C:\Users\EZ-Control>pip -V
pip 25.1.1 from D:\python\Lib\site-packages\pip (python 3.12)

C:\Users\EZ-Control>pip list
Package                 Version
----------------------- -----------
asttokens               3.0.0
beautifulsoup4          4.14.2
bqplot                  0.12.45
certifi                 2025.7.14
charset-normalizer      3.4.2
colorama                0.4.6
comm                    0.2.3
debugpy                 1.8.17
decorator               5.2.1
executing               2.2.1
fastcore                1.8.12
gast                    0.4.0
idna                    3.10
ipydatagrid             1.2.1
ipykernel               6.30.1
ipython                 9.6.0
ipython_pygments_lexers 1.1.1
ipywidgets              8.1.7
jedi                    0.19.2
jupyter_client          8.6.3
jupyter_core            5.8.1
jupyterlab_widgets      3.0.15
matplotlib-inline       0.1.7
nbstata                 0.8.3
nest-asyncio            1.6.0
numpy                   1.26.4
packaging               25.0
pandas                  2.3.1
parso                   0.8.5
pillow                  10.2.0
pip                     25.1.1
platformdirs            4.4.0
prompt_toolkit          3.0.52
psutil                  7.1.0
pure_eval               0.2.3
py2vega                 0.6.1
Pygments                2.19.2
python-dateutil         2.9.0.post0
pytz                    2025.2
pywin32                 311
pyzmq                   27.1.0
requests                2.32.4
six                     1.17.0
somepackage             1.2.3
soupsieve               2.8
stack-data              0.6.3
tornado                 6.5.2
tqdm                    4.67.1
traitlets               5.14.3
traittypes              0.2.1
typing_extensions       4.15.0
tzdata                  2025.2
urllib3                 2.5.0
wcwidth                 0.2.14
widgetsnbextension      4.0.14

C:\Users\EZ-Control>venv list
'venv' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\EZ-Control>pytnon -m venv list
'pytnon' is not recognized as an internal or external command,
operable program or batch file.

C:\Users\EZ-Control>pip install jupyter notebook
Collecting jupyter
  Downloading jupyter-1.1.1-py2.py3-none-any.whl.metadata (2.0 kB)
Collecting notebook
  Downloading notebook-7.4.7-py3-none-any.whl.metadata (10 kB)
Collecting jupyter-console (from jupyter)
  Downloading jupyter_console-6.6.3-py3-none-any.whl.metadata (5.8 kB)
Collecting nbconvert (from jupyter)
  Downloading nbconvert-7.16.6-py3-none-any.whl.metadata (8.5 kB)
Requirement already satisfied: ipykernel in d:\python\lib\site-packages (from jupyter) (6.30.1)
Requirement already satisfied: ipywidgets in d:\python\lib\site-packages (from jupyter) (8.1.7)
Collecting jupyterlab (from jupyter)
  Downloading jupyterlab-4.4.9-py3-none-any.whl.metadata (16 kB)
Collecting jupyter-server<3,>=2.4.0 (from notebook)
  Downloading jupyter_server-2.17.0-py3-none-any.whl.metadata (8.5 kB)
Collecting jupyterlab-server<3,>=2.27.1 (from notebook)
  Downloading jupyterlab_server-2.27.3-py3-none-any.whl.metadata (5.9 kB)
Collecting notebook-shim<0.3,>=0.2 (from notebook)
  Downloading notebook_shim-0.2.4-py3-none-any.whl.metadata (4.0 kB)
Requirement already satisfied: tornado>=6.2.0 in d:\python\lib\site-packages (from notebook) (6.5.2)
Collecting anyio>=3.1.0 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading anyio-4.11.0-py3-none-any.whl.metadata (4.1 kB)
Collecting argon2-cffi>=21.1 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading argon2_cffi-25.1.0-py3-none-any.whl.metadata (4.1 kB)
Collecting jinja2>=3.0.3 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading jinja2-3.1.6-py3-none-any.whl.metadata (2.9 kB)
Requirement already satisfied: jupyter-client>=7.4.4 in d:\python\lib\site-packages (from jupyter-server<3,>=2.4.0->notebook) (8.6.3)
Requirement already satisfied: jupyter-core!=5.0.*,>=4.12 in d:\python\lib\site-packages (from jupyter-server<3,>=2.4.0->notebook) (5.8.1)
Collecting jupyter-events>=0.11.0 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading jupyter_events-0.12.0-py3-none-any.whl.metadata (5.8 kB)
Collecting jupyter-server-terminals>=0.4.4 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading jupyter_server_terminals-0.5.3-py3-none-any.whl.metadata (5.6 kB)
Collecting nbformat>=5.3.0 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading nbformat-5.10.4-py3-none-any.whl.metadata (3.6 kB)
Requirement already satisfied: packaging>=22.0 in d:\python\lib\site-packages (from jupyter-server<3,>=2.4.0->notebook) (25.0)
Collecting prometheus-client>=0.9 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading prometheus_client-0.23.1-py3-none-any.whl.metadata (1.9 kB)
Collecting pywinpty>=2.0.1 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading pywinpty-3.0.0-cp312-cp312-win_amd64.whl.metadata (101 bytes)
Requirement already satisfied: pyzmq>=24 in d:\python\lib\site-packages (from jupyter-server<3,>=2.4.0->notebook) (27.1.0)
Collecting send2trash>=1.8.2 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading Send2Trash-1.8.3-py3-none-any.whl.metadata (4.0 kB)
Collecting terminado>=0.8.3 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading terminado-0.18.1-py3-none-any.whl.metadata (5.8 kB)
Requirement already satisfied: traitlets>=5.6.0 in d:\python\lib\site-packages (from jupyter-server<3,>=2.4.0->notebook) (5.14.3)
Collecting websocket-client>=1.7 (from jupyter-server<3,>=2.4.0->notebook)
  Downloading websocket_client-1.8.0-py3-none-any.whl.metadata (8.0 kB)
Collecting async-lru>=1.0.0 (from jupyterlab->jupyter)
  Downloading async_lru-2.0.5-py3-none-any.whl.metadata (4.5 kB)
Collecting httpx<1,>=0.25.0 (from jupyterlab->jupyter)
  Downloading httpx-0.28.1-py3-none-any.whl.metadata (7.1 kB)
Collecting jupyter-lsp>=2.0.0 (from jupyterlab->jupyter)
  Downloading jupyter_lsp-2.3.0-py3-none-any.whl.metadata (1.8 kB)
Collecting setuptools>=41.1.0 (from jupyterlab->jupyter)
  Downloading setuptools-80.9.0-py3-none-any.whl.metadata (6.6 kB)
Requirement already satisfied: certifi in d:\python\lib\site-packages (from httpx<1,>=0.25.0->jupyterlab->jupyter) (2025.7.14)
Collecting httpcore==1.* (from httpx<1,>=0.25.0->jupyterlab->jupyter)
  Downloading httpcore-1.0.9-py3-none-any.whl.metadata (21 kB)
Requirement already satisfied: idna in d:\python\lib\site-packages (from httpx<1,>=0.25.0->jupyterlab->jupyter) (3.10)
Collecting h11>=0.16 (from httpcore==1.*->httpx<1,>=0.25.0->jupyterlab->jupyter)
  Downloading h11-0.16.0-py3-none-any.whl.metadata (8.3 kB)
Collecting babel>=2.10 (from jupyterlab-server<3,>=2.27.1->notebook)
  Downloading babel-2.17.0-py3-none-any.whl.metadata (2.0 kB)
Collecting json5>=0.9.0 (from jupyterlab-server<3,>=2.27.1->notebook)
  Downloading json5-0.12.1-py3-none-any.whl.metadata (36 kB)
Collecting jsonschema>=4.18.0 (from jupyterlab-server<3,>=2.27.1->notebook)
  Downloading jsonschema-4.25.1-py3-none-any.whl.metadata (7.6 kB)
Requirement already satisfied: requests>=2.31 in d:\python\lib\site-packages (from jupyterlab-server<3,>=2.27.1->notebook) (2.32.4)
Collecting sniffio>=1.1 (from anyio>=3.1.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading sniffio-1.3.1-py3-none-any.whl.metadata (3.9 kB)
Requirement already satisfied: typing_extensions>=4.5 in d:\python\lib\site-packages (from anyio>=3.1.0->jupyter-server<3,>=2.4.0->notebook) (4.15.0)
Collecting argon2-cffi-bindings (from argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->notebook)
  Downloading argon2_cffi_bindings-25.1.0-cp39-abi3-win_amd64.whl.metadata (7.5 kB)
Requirement already satisfied: comm>=0.1.1 in d:\python\lib\site-packages (from ipykernel->jupyter) (0.2.3)
Requirement already satisfied: debugpy>=1.6.5 in d:\python\lib\site-packages (from ipykernel->jupyter) (1.8.17)
Requirement already satisfied: ipython>=7.23.1 in d:\python\lib\site-packages (from ipykernel->jupyter) (9.6.0)
Requirement already satisfied: matplotlib-inline>=0.1 in d:\python\lib\site-packages (from ipykernel->jupyter) (0.1.7)
Requirement already satisfied: nest-asyncio>=1.4 in d:\python\lib\site-packages (from ipykernel->jupyter) (1.6.0)
Requirement already satisfied: psutil>=5.7 in d:\python\lib\site-packages (from ipykernel->jupyter) (7.1.0)
Requirement already satisfied: colorama in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (0.4.6)
Requirement already satisfied: decorator in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (5.2.1)
Requirement already satisfied: ipython-pygments-lexers in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (1.1.1)
Requirement already satisfied: jedi>=0.16 in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (0.19.2)
Requirement already satisfied: prompt_toolkit<3.1.0,>=3.0.41 in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (3.0.52)
Requirement already satisfied: pygments>=2.4.0 in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (2.19.2)
Requirement already satisfied: stack_data in d:\python\lib\site-packages (from ipython>=7.23.1->ipykernel->jupyter) (0.6.3)
Requirement already satisfied: wcwidth in d:\python\lib\site-packages (from prompt_toolkit<3.1.0,>=3.0.41->ipython>=7.23.1->ipykernel->jupyter) (0.2.14)
Requirement already satisfied: parso<0.9.0,>=0.8.4 in d:\python\lib\site-packages (from jedi>=0.16->ipython>=7.23.1->ipykernel->jupyter) (0.8.5)
Collecting MarkupSafe>=2.0 (from jinja2>=3.0.3->jupyter-server<3,>=2.4.0->notebook)
  Downloading markupsafe-3.0.3-cp312-cp312-win_amd64.whl.metadata (2.8 kB)
Collecting attrs>=22.2.0 (from jsonschema>=4.18.0->jupyterlab-server<3,>=2.27.1->notebook)
  Downloading attrs-25.3.0-py3-none-any.whl.metadata (10 kB)
Collecting jsonschema-specifications>=2023.03.6 (from jsonschema>=4.18.0->jupyterlab-server<3,>=2.27.1->notebook)
  Downloading jsonschema_specifications-2025.9.1-py3-none-any.whl.metadata (2.9 kB)
Collecting referencing>=0.28.4 (from jsonschema>=4.18.0->jupyterlab-server<3,>=2.27.1->notebook)
  Downloading referencing-0.36.2-py3-none-any.whl.metadata (2.8 kB)
Collecting rpds-py>=0.7.1 (from jsonschema>=4.18.0->jupyterlab-server<3,>=2.27.1->notebook)
  Downloading rpds_py-0.27.1-cp312-cp312-win_amd64.whl.metadata (4.3 kB)
Requirement already satisfied: python-dateutil>=2.8.2 in d:\python\lib\site-packages (from jupyter-client>=7.4.4->jupyter-server<3,>=2.4.0->notebook) (2.9.0.post0)
Requirement already satisfied: platformdirs>=2.5 in d:\python\lib\site-packages (from jupyter-core!=5.0.*,>=4.12->jupyter-server<3,>=2.4.0->notebook) (4.4.0)
Requirement already satisfied: pywin32>=300 in d:\python\lib\site-packages (from jupyter-core!=5.0.*,>=4.12->jupyter-server<3,>=2.4.0->notebook) (311)
Collecting python-json-logger>=2.0.4 (from jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading python_json_logger-3.3.0-py3-none-any.whl.metadata (4.0 kB)
Collecting pyyaml>=5.3 (from jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading pyyaml-6.0.3-cp312-cp312-win_amd64.whl.metadata (2.4 kB)
Collecting rfc3339-validator (from jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading rfc3339_validator-0.1.4-py2.py3-none-any.whl.metadata (1.5 kB)
Collecting rfc3986-validator>=0.1.1 (from jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading rfc3986_validator-0.1.1-py2.py3-none-any.whl.metadata (1.7 kB)
Collecting fqdn (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading fqdn-1.5.1-py3-none-any.whl.metadata (1.4 kB)
Collecting isoduration (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading isoduration-20.11.0-py3-none-any.whl.metadata (5.7 kB)
Collecting jsonpointer>1.13 (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading jsonpointer-3.0.0-py2.py3-none-any.whl.metadata (2.3 kB)
Collecting rfc3987-syntax>=1.1.0 (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading rfc3987_syntax-1.1.0-py3-none-any.whl.metadata (7.7 kB)
Collecting uri-template (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading uri_template-1.3.0-py3-none-any.whl.metadata (8.8 kB)
Collecting webcolors>=24.6.0 (from jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading webcolors-24.11.1-py3-none-any.whl.metadata (2.2 kB)
Requirement already satisfied: beautifulsoup4 in d:\python\lib\site-packages (from nbconvert->jupyter) (4.14.2)
Collecting bleach!=5.0.0 (from bleach[css]!=5.0.0->nbconvert->jupyter)
  Downloading bleach-6.2.0-py3-none-any.whl.metadata (30 kB)
Collecting defusedxml (from nbconvert->jupyter)
  Downloading defusedxml-0.7.1-py2.py3-none-any.whl.metadata (32 kB)
Collecting jupyterlab-pygments (from nbconvert->jupyter)
  Downloading jupyterlab_pygments-0.3.0-py3-none-any.whl.metadata (4.4 kB)
Collecting mistune<4,>=2.0.3 (from nbconvert->jupyter)
  Downloading mistune-3.1.4-py3-none-any.whl.metadata (1.8 kB)
Collecting nbclient>=0.5.0 (from nbconvert->jupyter)
  Downloading nbclient-0.10.2-py3-none-any.whl.metadata (8.3 kB)
Collecting pandocfilters>=1.4.1 (from nbconvert->jupyter)
  Downloading pandocfilters-1.5.1-py2.py3-none-any.whl.metadata (9.0 kB)
Collecting webencodings (from bleach!=5.0.0->bleach[css]!=5.0.0->nbconvert->jupyter)
  Downloading webencodings-0.5.1-py2.py3-none-any.whl.metadata (2.1 kB)
Collecting tinycss2<1.5,>=1.1.0 (from bleach[css]!=5.0.0->nbconvert->jupyter)
  Downloading tinycss2-1.4.0-py3-none-any.whl.metadata (3.0 kB)
Collecting fastjsonschema>=2.15 (from nbformat>=5.3.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading fastjsonschema-2.21.2-py3-none-any.whl.metadata (2.3 kB)
Requirement already satisfied: six>=1.5 in d:\python\lib\site-packages (from python-dateutil>=2.8.2->jupyter-client>=7.4.4->jupyter-server<3,>=2.4.0->notebook) (1.17.0)
Requirement already satisfied: charset_normalizer<4,>=2 in d:\python\lib\site-packages (from requests>=2.31->jupyterlab-server<3,>=2.27.1->notebook) (3.4.2)
Requirement already satisfied: urllib3<3,>=1.21.1 in d:\python\lib\site-packages (from requests>=2.31->jupyterlab-server<3,>=2.27.1->notebook) (2.5.0)
Collecting lark>=1.2.2 (from rfc3987-syntax>=1.1.0->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading lark-1.3.0-py3-none-any.whl.metadata (1.8 kB)
Collecting cffi>=1.0.1 (from argon2-cffi-bindings->argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->notebook)
  Downloading cffi-2.0.0-cp312-cp312-win_amd64.whl.metadata (2.6 kB)
Collecting pycparser (from cffi>=1.0.1->argon2-cffi-bindings->argon2-cffi>=21.1->jupyter-server<3,>=2.4.0->notebook)
  Downloading pycparser-2.23-py3-none-any.whl.metadata (993 bytes)
Requirement already satisfied: soupsieve>1.2 in d:\python\lib\site-packages (from beautifulsoup4->nbconvert->jupyter) (2.8)
Requirement already satisfied: widgetsnbextension~=4.0.14 in d:\python\lib\site-packages (from ipywidgets->jupyter) (4.0.14)
Requirement already satisfied: jupyterlab_widgets~=3.0.15 in d:\python\lib\site-packages (from ipywidgets->jupyter) (3.0.15)
Collecting arrow>=0.15.0 (from isoduration->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading arrow-1.3.0-py3-none-any.whl.metadata (7.5 kB)
Collecting types-python-dateutil>=2.8.10 (from arrow>=0.15.0->isoduration->jsonschema[format-nongpl]>=4.18.0->jupyter-events>=0.11.0->jupyter-server<3,>=2.4.0->notebook)
  Downloading types_python_dateutil-2.9.0.20250822-py3-none-any.whl.metadata (1.8 kB)
Requirement already satisfied: executing>=1.2.0 in d:\python\lib\site-packages (from stack_data->ipython>=7.23.1->ipykernel->jupyter) (2.2.1)
Requirement already satisfied: asttokens>=2.1.0 in d:\python\lib\site-packages (from stack_data->ipython>=7.23.1->ipykernel->jupyter) (3.0.0)
Requirement already satisfied: pure-eval in d:\python\lib\site-packages (from stack_data->ipython>=7.23.1->ipykernel->jupyter) (0.2.3)
Downloading jupyter-1.1.1-py2.py3-none-any.whl (2.7 kB)
Downloading notebook-7.4.7-py3-none-any.whl (14.3 MB)
   ---------------------------------------- 14.3/14.3 MB 7.8 MB/s eta 0:00:00
Downloading jupyter_server-2.17.0-py3-none-any.whl (388 kB)
Downloading jupyterlab-4.4.9-py3-none-any.whl (12.3 MB)
   ---------------------------------------- 12.3/12.3 MB 12.4 MB/s eta 0:00:00
Downloading httpx-0.28.1-py3-none-any.whl (73 kB)
Downloading httpcore-1.0.9-py3-none-any.whl (78 kB)
Downloading jupyterlab_server-2.27.3-py3-none-any.whl (59 kB)
Downloading notebook_shim-0.2.4-py3-none-any.whl (13 kB)
Downloading anyio-4.11.0-py3-none-any.whl (109 kB)
Downloading argon2_cffi-25.1.0-py3-none-any.whl (14 kB)
Downloading async_lru-2.0.5-py3-none-any.whl (6.1 kB)
Downloading babel-2.17.0-py3-none-any.whl (10.2 MB)
   ---------------------------------------- 10.2/10.2 MB 11.3 MB/s eta 0:00:00
Downloading h11-0.16.0-py3-none-any.whl (37 kB)
Downloading jinja2-3.1.6-py3-none-any.whl (134 kB)
Downloading json5-0.12.1-py3-none-any.whl (36 kB)
Downloading jsonschema-4.25.1-py3-none-any.whl (90 kB)
Downloading attrs-25.3.0-py3-none-any.whl (63 kB)
Downloading jsonschema_specifications-2025.9.1-py3-none-any.whl (18 kB)
Downloading jupyter_events-0.12.0-py3-none-any.whl (19 kB)
Downloading jsonpointer-3.0.0-py2.py3-none-any.whl (7.6 kB)
Downloading jupyter_lsp-2.3.0-py3-none-any.whl (76 kB)
Downloading jupyter_server_terminals-0.5.3-py3-none-any.whl (13 kB)
Downloading markupsafe-3.0.3-cp312-cp312-win_amd64.whl (15 kB)
Downloading nbconvert-7.16.6-py3-none-any.whl (258 kB)
Downloading mistune-3.1.4-py3-none-any.whl (53 kB)
Downloading bleach-6.2.0-py3-none-any.whl (163 kB)
Downloading tinycss2-1.4.0-py3-none-any.whl (26 kB)
Downloading nbclient-0.10.2-py3-none-any.whl (25 kB)
Downloading nbformat-5.10.4-py3-none-any.whl (78 kB)
Downloading fastjsonschema-2.21.2-py3-none-any.whl (24 kB)
Downloading pandocfilters-1.5.1-py2.py3-none-any.whl (8.7 kB)
Downloading prometheus_client-0.23.1-py3-none-any.whl (61 kB)
Downloading python_json_logger-3.3.0-py3-none-any.whl (15 kB)
Downloading pywinpty-3.0.0-cp312-cp312-win_amd64.whl (2.1 MB)
   ---------------------------------------- 2.1/2.1 MB 10.4 MB/s eta 0:00:00
Downloading pyyaml-6.0.3-cp312-cp312-win_amd64.whl (154 kB)
Downloading referencing-0.36.2-py3-none-any.whl (26 kB)
Downloading rfc3986_validator-0.1.1-py2.py3-none-any.whl (4.2 kB)
Downloading rfc3987_syntax-1.1.0-py3-none-any.whl (8.0 kB)
Downloading lark-1.3.0-py3-none-any.whl (113 kB)
Downloading rpds_py-0.27.1-cp312-cp312-win_amd64.whl (232 kB)
Downloading Send2Trash-1.8.3-py3-none-any.whl (18 kB)
Downloading setuptools-80.9.0-py3-none-any.whl (1.2 MB)
   ---------------------------------------- 1.2/1.2 MB 12.0 MB/s eta 0:00:00
Downloading sniffio-1.3.1-py3-none-any.whl (10 kB)
Downloading terminado-0.18.1-py3-none-any.whl (14 kB)
Downloading webcolors-24.11.1-py3-none-any.whl (14 kB)
Downloading webencodings-0.5.1-py2.py3-none-any.whl (11 kB)
Downloading websocket_client-1.8.0-py3-none-any.whl (58 kB)
Downloading argon2_cffi_bindings-25.1.0-cp39-abi3-win_amd64.whl (31 kB)
Downloading cffi-2.0.0-cp312-cp312-win_amd64.whl (183 kB)
Downloading defusedxml-0.7.1-py2.py3-none-any.whl (25 kB)
Downloading fqdn-1.5.1-py3-none-any.whl (9.1 kB)
Downloading isoduration-20.11.0-py3-none-any.whl (11 kB)
Downloading arrow-1.3.0-py3-none-any.whl (66 kB)
Downloading types_python_dateutil-2.9.0.20250822-py3-none-any.whl (17 kB)
Downloading jupyter_console-6.6.3-py3-none-any.whl (24 kB)
Downloading jupyterlab_pygments-0.3.0-py3-none-any.whl (15 kB)
Downloading pycparser-2.23-py3-none-any.whl (118 kB)
Downloading rfc3339_validator-0.1.4-py2.py3-none-any.whl (3.5 kB)
Downloading uri_template-1.3.0-py3-none-any.whl (11 kB)
Installing collected packages: webencodings, fastjsonschema, websocket-client, webcolors, uri-template, types-python-dateutil, tinycss2, sniffio, setuptools, send2trash, rpds-py, rfc3986-validator, rfc3339-validator, pyyaml, pywinpty, python-json-logger, pycparser, prometheus-client, pandocfilters, mistune, MarkupSafe, lark, jupyterlab-pygments, jsonpointer, json5, h11, fqdn, defusedxml, bleach, babel, attrs, async-lru, terminado, rfc3987-syntax, referencing, jinja2, httpcore, cffi, arrow, anyio, jupyter-server-terminals, jsonschema-specifications, isoduration, httpx, argon2-cffi-bindings, jupyter-console, jsonschema, argon2-cffi, nbformat, nbclient, jupyter-events, nbconvert, jupyter-server, notebook-shim, jupyterlab-server, jupyter-lsp, jupyterlab, notebook, jupyter
Successfully installed MarkupSafe-3.0.3 anyio-4.11.0 argon2-cffi-25.1.0 argon2-cffi-bindings-25.1.0 arrow-1.3.0 async-lru-2.0.5 attrs-25.3.0 babel-2.17.0 bleach-6.2.0 cffi-2.0.0 defusedxml-0.7.1 fastjsonschema-2.21.2 fqdn-1.5.1 h11-0.16.0 httpcore-1.0.9 httpx-0.28.1 isoduration-20.11.0 jinja2-3.1.6 json5-0.12.1 jsonpointer-3.0.0 jsonschema-4.25.1 jsonschema-specifications-2025.9.1 jupyter-1.1.1 jupyter-console-6.6.3 jupyter-events-0.12.0 jupyter-lsp-2.3.0 jupyter-server-2.17.0 jupyter-server-terminals-0.5.3 jupyterlab-4.4.9 jupyterlab-pygments-0.3.0 jupyterlab-server-2.27.3 lark-1.3.0 mistune-3.1.4 nbclient-0.10.2 nbconvert-7.16.6 nbformat-5.10.4 notebook-7.4.7 notebook-shim-0.2.4 pandocfilters-1.5.1 prometheus-client-0.23.1 pycparser-2.23 python-json-logger-3.3.0 pywinpty-3.0.0 pyyaml-6.0.3 referencing-0.36.2 rfc3339-validator-0.1.4 rfc3986-validator-0.1.1 rfc3987-syntax-1.1.0 rpds-py-0.27.1 send2trash-1.8.3 setuptools-80.9.0 sniffio-1.3.1 terminado-0.18.1 tinycss2-1.4.0 types-python-dateutil-2.9.0.20250822 uri-template-1.3.0 webcolors-24.11.1 webencodings-0.5.1 websocket-client-1.8.0

[notice] A new release of pip is available: 25.1.1 -> 25.2
[notice] To update, run: python.exe -m pip install --upgrade pip

C:\Users\EZ-Control>
