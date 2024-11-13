### 项目构建
#### 切换项目到v0.1tag并创建对应该tag的分支
```shell
~/Documents/LLM_PROJECT/PYTHON/GitHubSentinel on  branch_v0.0.1 ⌚ 10:45:40
$ git checkout -b branch_v0.1 v0.1

Switched to a new branch 'branch_v0.1'
(git-hub-sentinel) 
```
### 创建项目运行环境
```shell
~/Documents/LLM_PROJECT/PYTHON/GitHubSentinel on  branch_v0.1 ⌚ 10:35:40
$ conda create -n git-hub-sentinel python=3.10

Retrieving notices: ...working... done
Channels:
 - defaults
Platform: osx-64
Collecting package metadata (repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /opt/miniconda3/envs/git-hub-sentinel

  added / updated specs:
    - python=3.10


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    pip-24.2                   |  py310hecd8cb5_0         2.3 MB
    python-3.10.15             |       hce00570_1        13.2 MB
    setuptools-75.1.0          |  py310hecd8cb5_0         1.7 MB
    tzdata-2024b               |       h04d1e81_0         115 KB
    wheel-0.44.0               |  py310hecd8cb5_0         113 KB
    ------------------------------------------------------------
                                           Total:        17.4 MB

The following NEW packages will be INSTALLED:

  bzip2              pkgs/main/osx-64::bzip2-1.0.8-h6c40b1e_6 
  ca-certificates    pkgs/main/osx-64::ca-certificates-2024.9.24-hecd8cb5_0 
  libffi             pkgs/main/osx-64::libffi-3.4.4-hecd8cb5_1 
  ncurses            pkgs/main/osx-64::ncurses-6.4-hcec6c5f_0 
  openssl            pkgs/main/osx-64::openssl-3.0.15-h46256e1_0 
  pip                pkgs/main/osx-64::pip-24.2-py310hecd8cb5_0 
  python             pkgs/main/osx-64::python-3.10.15-hce00570_1 
  readline           pkgs/main/osx-64::readline-8.2-hca72f7f_0 
  setuptools         pkgs/main/osx-64::setuptools-75.1.0-py310hecd8cb5_0 
  sqlite             pkgs/main/osx-64::sqlite-3.45.3-h6c40b1e_0 
  tk                 pkgs/main/osx-64::tk-8.6.14-h4d00af3_0 
  tzdata             pkgs/main/noarch::tzdata-2024b-h04d1e81_0 
  wheel              pkgs/main/osx-64::wheel-0.44.0-py310hecd8cb5_0 
  xz                 pkgs/main/osx-64::xz-5.4.6-h6c40b1e_1 
  zlib               pkgs/main/osx-64::zlib-1.2.13-h4b97444_1 


Proceed ([y]/n)? y


Downloading and Extracting Packages:
                                                                                                                                                                                                                           
Preparing transaction: done                                                                                                                                                                                                
Verifying transaction: done                                                                                                                                                                                                
Executing transaction: done                                                                                                                                                                                                
#                                                                                                                                                                                                                          
# To activate this environment, use
#
#     $ conda activate git-hub-sentinel
#
# To deactivate an active environment, use
#
#     $ conda deactivate

(base) 
~/Documents/LLM_PROJECT/PYTHON/GitHubSentinel on  branch_v0.1 ⌚ 10:38:14
$  conda activate git-hub-sentinel
(git-hub-sentinel) 
~/Documents/LLM_PROJECT/PYTHON/GitHubSentinel on  branch_v0.1 ⌚ 10:38:26
$ pip install -r requirements.txt

Looking in indexes: https://mirrors.aliyun.com/pypi/simple/
Collecting requests (from -r requirements.txt (line 1))
  Downloading https://mirrors.aliyun.com/pypi/packages/f9/9b/335f9764261e915ed497fcdeb11df5dfd6f7bf257d4a6a2a686d80da4d54/requests-2.32.3-py3-none-any.whl (64 kB)
Collecting charset-normalizer<4,>=2 (from requests->-r requirements.txt (line 1))
  Downloading https://mirrors.aliyun.com/pypi/packages/23/81/d7eef6a99e42c77f444fdd7bc894b0ceca6c3a95c51239e74a722039521c/charset_normalizer-3.4.0-cp310-cp310-macosx_10_9_x86_64.whl (125 kB)
Collecting idna<4,>=2.5 (from requests->-r requirements.txt (line 1))
  Downloading https://mirrors.aliyun.com/pypi/packages/76/c6/c88e154df9c4e1a2a66ccf0005a88dfb2650c1dffb6f5ce603dfbd452ce3/idna-3.10-py3-none-any.whl (70 kB)
Collecting urllib3<3,>=1.21.1 (from requests->-r requirements.txt (line 1))
  Downloading https://mirrors.aliyun.com/pypi/packages/ce/d9/5f4c13cecde62396b0d3fe530a50ccea91e7dfc1ccf0e09c228841bb5ba8/urllib3-2.2.3-py3-none-any.whl (126 kB)
Collecting certifi>=2017.4.17 (from requests->-r requirements.txt (line 1))
  Downloading https://mirrors.aliyun.com/pypi/packages/12/90/3c9ff0512038035f59d279fddeb79f5f1eccd8859f06d6163c58798b9487/certifi-2024.8.30-py3-none-any.whl (167 kB)
Installing collected packages: urllib3, idna, charset-normalizer, certifi, requests
Successfully installed certifi-2024.8.30 charset-normalizer-3.4.0 idna-3.10 requests-2.32.3 urllib3-2.2.3
(git-hub-sentinel) 


~/Documents/LLM_PROJECT/PYTHON/GitHubSentinel on  branch_v0.1 ⌚ 10:45:42
$ pip install -r requirements.txt 

Looking in indexes: https://mirrors.aliyun.com/pypi/simple/
Requirement already satisfied: requests in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from -r requirements.txt (line 1)) (2.32.3)
Requirement already satisfied: charset-normalizer<4,>=2 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (3.4.0)
Requirement already satisfied: idna<4,>=2.5 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (3.10)
Requirement already satisfied: urllib3<3,>=1.21.1 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (2.2.3)
Requirement already satisfied: certifi>=2017.4.17 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (2024.8.30)
(git-hub-sentinel) 
```
### 配置项目config.json文件
> 对应的`github_token`在页面`https://github.com/settings/tokens?page=1&type=beta`中,复制粘贴.

### 项目启动
```shell
~/Documents/LLM_PROJECT/PYTHON/GitHubSentinel on  branch_v0.1! ⌚ 10:46:09
$ python src/main.py              

GitHub Sentinel Command Line Interface

Available commands:
  add <repo>       Add a subscription (e.g., owner/repo)
  remove <repo>    Remove a subscription (e.g., owner/repo)
  list             List all subscriptions
  fetch            Fetch updates immediately
  help             Show this help message
  exit             Exit the tool
  quit             Exit the tool

GitHub Sentinel> fetch
Updates fetched:
Latest Release Information:

Repository: langchain-ai/langchain
Latest Version: langchain-qdrant==0.2.0
Release Name: langchain-qdrant==0.2.0
Published at: 2024-11-05T20:51:40Z
Release Notes:
Changes since langchain-qdrant==0.1.4

qdrant,nomic[minor]: bump core deps (#27849)
multiple: rely on asyncio_mode auto in tests (#27200)
----------------------------------------

GitHub Sentinel>  list
Current subscriptions:
- langchain-ai/langchain
GitHub Sentinel> help

GitHub Sentinel Command Line Interface

Available commands:
  add <repo>       Add a subscription (e.g., owner/repo)
  remove <repo>    Remove a subscription (e.g., owner/repo)
  list             List all subscriptions
  fetch            Fetch updates immediately
  help             Show this help message
  exit             Exit the tool
  quit             Exit the tool

GitHub Sentinel> exit
Exiting GitHub Sentinel...
(git-hub-sentinel) 
```
