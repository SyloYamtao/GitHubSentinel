### 同步fork仓库标签

```shell
~/Documents/LLM_PROJECT/PYTHON/ForkGitHubSentinel on  main ⌚ 10:27:17
$ git remote add upstream git@github.com:DjangoPeng/GitHubSentinel.git   

~/Documents/LLM_PROJECT/PYTHON/ForkGitHubSentinel on  main ⌚ 10:30:58
$ git fetch upstream --tags
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 3 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), done.
From github.com:DjangoPeng/GitHubSentinel
 * [new branch]      main       -> upstream/main
 * [new branch]      v0.2.1     -> upstream/v0.2.1
 * [new branch]      v0.3       -> upstream/v0.3
 * [new branch]      v0.3.2     -> upstream/v0.3.2
 * [new branch]      v0.4       -> upstream/v0.4
 * [new branch]      v0.4.1     -> upstream/v0.4.1
 * [new branch]      v0.5       -> upstream/v0.5
 * [new branch]      v0.6       -> upstream/v0.6
 * [new branch]      v0.7       -> upstream/v0.7
 * [new branch]      v0.8       -> upstream/v0.8
 * [new branch]      v0.8.1     -> upstream/v0.8.1
 * [new branch]      v0.8.2     -> upstream/v0.8.2
 * [new tag]         v0.0.1     -> v0.0.1
 * [new tag]         v0.1       -> v0.1
 * [new tag]         v0.2       -> v0.2
 * [new tag]         v0.2.1     -> v0.2.1
 * [new tag]         v0.3       -> v0.3
 * [new tag]         v0.3.1     -> v0.3.1
 * [new tag]         v0.3.2     -> v0.3.2
 * [new tag]         v0.4       -> v0.4
 * [new tag]         v0.4.1     -> v0.4.1
 * [new tag]         v0.5       -> v0.5
 * [new tag]         v0.6       -> v0.6
 * [new tag]         v0.7       -> v0.7
 * [new tag]         v0.8       -> v0.8
 * [new tag]         v0.8.1     -> v0.8.1
 * [new tag]         v0.8.2     -> v0.8.2
(git-hub-sentinel) 

```

### 切换到0.3.2tag并且以此创建新的分支branch_v0.3.2

```shell
~/Documents/LLM_PROJECT/PYTHON/ForkGitHubSentinel on  main ⌚ 10:32:12
$ git checkout -b branch_v0.3.1 v0.3.1                             

Switched to a new branch 'branch_v0.3.1'

(git-hub-sentinel) 
```

### 安装requirements.txt相关依赖

#### requirements依赖

```text
requests
openai
gradio
loguru
```

```shell
$ pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple

Looking in indexes: https://pypi.tuna.tsinghua.edu.cn/simple
Requirement already satisfied: requests in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from -r requirements.txt (line 1)) (2.32.3)
Collecting openai (from -r requirements.txt (line 2))
  Using cached https://pypi.tuna.tsinghua.edu.cn/packages/c7/d8/3e4cf8a5f544bef575d3502fedd81a15e317f591022de940647bdd0cc017/openai-1.54.4-py3-none-any.whl (389 kB)
Collecting gradio (from -r requirements.txt (line 3))
  Using cached https://pypi.tuna.tsinghua.edu.cn/packages/18/a1/1bdb57a072903b222b1a745aa634cb845ff5f52a88ddd5ed1640ecf30beb/gradio-5.5.0-py3-none-any.whl (56.7 MB)
Requirement already satisfied: charset-normalizer<4,>=2 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (3.4.0)
Requirement already satisfied: idna<4,>=2.5 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (3.10)
Requirement already satisfied: urllib3<3,>=1.21.1 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (2.2.3)
Requirement already satisfied: certifi>=2017.4.17 in /opt/miniconda3/envs/git-hub-sentinel/lib/python3.10/site-packages (from requests->-r requirements.txt (line 1)) (2024.8.30)
Collecting anyio<5,>=3.5.0 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/e4/f5/f2b75d2fc6f1a260f340f0e7c6a060f4dd2961cc16884ed851b0d18da06a/anyio-4.6.2.post1-py3-none-any.whl (90 kB)
Collecting distro<2,>=1.7.0 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/12/b3/231ffd4ab1fc9d679809f356cebee130ac7daa00d6d6f3206dd4fd137e9e/distro-1.9.0-py3-none-any.whl (20 kB)
Collecting httpx<1,>=0.23.0 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/56/95/9377bcb415797e44274b51d46e3249eba641711cf3348050f76ee7b15ffc/httpx-0.27.2-py3-none-any.whl (76 kB)
Collecting jiter<1,>=0.4.0 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/36/f5/c6ccaa2331037cbb69d82e3ab2f2beaec485dd9e42a2ac409e6219b2d7f0/jiter-0.7.1-cp310-cp310-macosx_10_12_x86_64.whl (291 kB)
Collecting pydantic<3,>=1.9.0 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/df/e4/ba44652d562cbf0bf320e0f3810206149c8a4e99cdbf66da82e97ab53a15/pydantic-2.9.2-py3-none-any.whl (434 kB)
Collecting sniffio (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/e9/44/75a9c9421471a6c4805dbf2356f7c181a29c1879239abab1ea2cc8f38b40/sniffio-1.3.1-py3-none-any.whl (10 kB)
Collecting tqdm>4 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/2b/78/57043611a16c655c8350b4c01b8d6abfb38cc2acb475238b62c2146186d7/tqdm-4.67.0-py3-none-any.whl (78 kB)
Collecting typing-extensions<5,>=4.11 (from openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/26/9f/ad63fc0248c5379346306f8668cda6e2e2e9c95e01216d2b8ffd9ff037d0/typing_extensions-4.12.2-py3-none-any.whl (37 kB)
Collecting aiofiles<24.0,>=22.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/c5/19/5af6804c4cc0fed83f47bff6e413a98a36618e7d40185cd36e69737f3b0e/aiofiles-23.2.1-py3-none-any.whl (15 kB)
Collecting fastapi<1.0,>=0.115.2 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/54/c4/148d5046a96c428464557264877ae5a9338a83bbe0df045088749ec89820/fastapi-0.115.5-py3-none-any.whl (94 kB)
Collecting ffmpy (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/ff/1e/db99aa669eee301966bc6c997d60a0240f9cecae63f044b2e5a5310e4bf7/ffmpy-0.4.0-py3-none-any.whl (5.8 kB)
Collecting gradio-client==1.4.2 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/e0/6f/9eb14d4e9ef366be2020063d91c4f608294969fcd7b9fcc48153c64b9776/gradio_client-1.4.2-py3-none-any.whl (319 kB)
Collecting huggingface-hub>=0.25.1 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/60/bf/cea0b9720c32fa01b0c4ec4b16b9f4ae34ca106b202ebbae9f03ab98cd8f/huggingface_hub-0.26.2-py3-none-any.whl (447 kB)
Collecting jinja2<4.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/31/80/3a54838c3fb461f6fec263ebf3a3a41771bd05190238de3486aae8540c36/jinja2-3.1.4-py3-none-any.whl (133 kB)
Collecting markupsafe~=2.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/6a/4a/a4d49415e600bacae038c67f9fecc1d5433b9d3c71a4de6f33537b89654c/MarkupSafe-2.1.5-cp310-cp310-macosx_10_9_x86_64.whl (14 kB)
Collecting numpy<3.0,>=1.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/d1/bb/75b945874f931494891eac6ca06a1764d0e8208791f3addadb2963b83527/numpy-2.1.3-cp310-cp310-macosx_14_0_x86_64.whl (6.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 6.9/6.9 MB 2.8 MB/s eta 0:00:00
Collecting orjson~=3.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/3e/63/f7d412e09f6e2c4e2562ddc44e86f2316a7ce9d7f353afa7cbce4f6a78d5/orjson-3.10.11-cp310-cp310-macosx_10_15_x86_64.macosx_11_0_arm64.macosx_10_15_universal2.whl (266 kB)
Collecting packaging (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/88/ef/eb23f262cca3c0c4eb7ab1933c3b1f03d021f2c48f54763065b6f0e321be/packaging-24.2-py3-none-any.whl (65 kB)
Collecting pandas<3.0,>=1.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/aa/70/c853aec59839bceed032d52010ff5f1b8d87dc3114b762e4ba2727661a3b/pandas-2.2.3-cp310-cp310-macosx_10_9_x86_64.whl (12.6 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 12.6/12.6 MB 4.2 MB/s eta 0:00:00
Collecting pillow<12.0,>=8.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/98/fb/a6ce6836bd7fd93fbf9144bf54789e02babc27403b50a9e1583ee877d6da/pillow-11.0.0-cp310-cp310-macosx_10_10_x86_64.whl (3.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 3.2/3.2 MB 3.5 MB/s eta 0:00:00
Collecting pydub (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/a6/53/d78dc063216e62fc55f6b2eebb447f6a4b0a59f55c8406376f76bf959b08/pydub-0.25.1-py2.py3-none-any.whl (32 kB)
Collecting python-multipart==0.0.12 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/f5/0b/c316262244abea7481f95f1e91d7575f3dfcf6455d56d1ffe9839c582eb1/python_multipart-0.0.12-py3-none-any.whl (23 kB)
Collecting pyyaml<7.0,>=5.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/9b/95/a3fac87cb7158e231b5a6012e438c647e1a87f09f8e0d123acec8ab8bf71/PyYAML-6.0.2-cp310-cp310-macosx_10_9_x86_64.whl (184 kB)
Collecting ruff>=0.2.2 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/20/ea/1f0a22a6bcdd3fc26c73f63a025d05bd565901b729d56bcb093c722a6c4c/ruff-0.7.3-py3-none-macosx_10_12_x86_64.whl (10.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 10.2/10.2 MB 2.6 MB/s eta 0:00:00
Collecting safehttpx<1.0,>=0.1.1 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/df/f7/55cdeed5889f2076fdb125bc87bb7ab0f1715c84b0a4619c44833d890f60/safehttpx-0.1.1-py3-none-any.whl (8.4 kB)
Collecting semantic-version~=2.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/6a/23/8146aad7d88f4fcb3a6218f41a60f6c2d4e3a72de72da1825dc7c8f7877c/semantic_version-2.10.0-py2.py3-none-any.whl (15 kB)
Collecting starlette<1.0,>=0.40.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/54/43/f185bfd0ca1d213beb4293bed51d92254df23d8ceaf6c0e17146d508a776/starlette-0.41.2-py3-none-any.whl (73 kB)
Collecting tomlkit==0.12.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/68/4f/12207897848a653d03ebbf6775a29d949408ded5f99b2d87198bc5c93508/tomlkit-0.12.0-py3-none-any.whl (37 kB)
Collecting typer<1.0,>=0.12 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/18/7e/c8bfa8cbcd3ea1d25d2beb359b5c5a3f4339a7e2e5d9e3ef3e29ba3ab3b9/typer-0.13.0-py3-none-any.whl (44 kB)
Collecting uvicorn>=0.14.0 (from gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/eb/14/78bd0e95dd2444b6caacbca2b730671d4295ccb628ef58b81bee903629df/uvicorn-0.32.0-py3-none-any.whl (63 kB)
Collecting fsspec (from gradio-client==1.4.2->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/c6/b2/454d6e7f0158951d8a78c2e1eb4f69ae81beb8dca5fee9809c6c99e9d0d0/fsspec-2024.10.0-py3-none-any.whl (179 kB)
Collecting websockets<13.0,>=10.0 (from gradio-client==1.4.2->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/bb/d3/1eca0d8fb6f0665c96f0dc7c0d0ec8aa1a425e8c003e0c18e1451f65d177/websockets-12.0-cp310-cp310-macosx_10_9_x86_64.whl (121 kB)
Collecting exceptiongroup>=1.0.2 (from anyio<5,>=3.5.0->openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/02/cc/b7e31358aac6ed1ef2bb790a9746ac2c69bcb3c8588b41616914eb106eaf/exceptiongroup-1.2.2-py3-none-any.whl (16 kB)
Collecting httpcore==1.* (from httpx<1,>=0.23.0->openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/06/89/b161908e2f51be56568184aeb4a880fd287178d176fd1c860d2217f41106/httpcore-1.0.6-py3-none-any.whl (78 kB)
Collecting h11<0.15,>=0.13 (from httpcore==1.*->httpx<1,>=0.23.0->openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/95/04/ff642e65ad6b90db43e668d70ffb6736436c7ce41fcc549f4e9472234127/h11-0.14.0-py3-none-any.whl (58 kB)
Collecting filelock (from huggingface-hub>=0.25.1->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/b9/f8/feced7779d755758a52d1f6635d990b8d98dc0a29fa568bbe0625f18fdf3/filelock-3.16.1-py3-none-any.whl (16 kB)
Collecting python-dateutil>=2.8.2 (from pandas<3.0,>=1.0->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/ec/57/56b9bcc3c9c6a792fcbaf139543cee77261f3651ca9da0c93f5c1221264b/python_dateutil-2.9.0.post0-py2.py3-none-any.whl (229 kB)
Collecting pytz>=2020.1 (from pandas<3.0,>=1.0->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/11/c3/005fcca25ce078d2cc29fd559379817424e94885510568bc1bc53d7d5846/pytz-2024.2-py2.py3-none-any.whl (508 kB)
Collecting tzdata>=2022.7 (from pandas<3.0,>=1.0->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/a6/ab/7e5f53c3b9d14972843a647d8d7a853969a58aecc7559cb3267302c94774/tzdata-2024.2-py2.py3-none-any.whl (346 kB)
Collecting annotated-types>=0.6.0 (from pydantic<3,>=1.9.0->openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/78/b6/6307fbef88d9b5ee7421e68d78a9f162e0da4900bc5f5793f6d3d0e34fb8/annotated_types-0.7.0-py3-none-any.whl (13 kB)
Collecting pydantic-core==2.23.4 (from pydantic<3,>=1.9.0->openai->-r requirements.txt (line 2))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/5c/8b/d3ae387f66277bd8104096d6ec0a145f4baa2966ebb2cad746c0920c9526/pydantic_core-2.23.4-cp310-cp310-macosx_10_12_x86_64.whl (1.9 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.9/1.9 MB 2.7 MB/s eta 0:00:00
Collecting click>=8.0.0 (from typer<1.0,>=0.12->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/00/2e/d53fa4befbf2cfa713304affc7ca780ce4fc1fd8710527771b58311a3229/click-8.1.7-py3-none-any.whl (97 kB)
Collecting shellingham>=1.3.0 (from typer<1.0,>=0.12->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/e0/f9/0595336914c5619e5f28a1fb793285925a8cd4b432c9da0a987836c7f822/shellingham-1.5.4-py2.py3-none-any.whl (9.8 kB)
Collecting rich>=10.11.0 (from typer<1.0,>=0.12->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/19/71/39c7c0d87f8d4e6c020a393182060eaefeeae6c01dab6a84ec346f2567df/rich-13.9.4-py3-none-any.whl (242 kB)
Collecting six>=1.5 (from python-dateutil>=2.8.2->pandas<3.0,>=1.0->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/d9/5a/e7c31adbe875f2abbb91bd84cf2dc52d792b5a01506781dbcf25c91daf11/six-1.16.0-py2.py3-none-any.whl (11 kB)
Collecting markdown-it-py>=2.2.0 (from rich>=10.11.0->typer<1.0,>=0.12->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/42/d7/1ec15b46af6af88f19b8e5ffea08fa375d433c998b8a7639e76935c14f1f/markdown_it_py-3.0.0-py3-none-any.whl (87 kB)
Collecting pygments<3.0.0,>=2.13.0 (from rich>=10.11.0->typer<1.0,>=0.12->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/f7/3f/01c8b82017c199075f8f788d0d906b9ffbbc5a47dc9918a945e13d5a2bda/pygments-2.18.0-py3-none-any.whl (1.2 MB)
     ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━ 1.2/1.2 MB 832.2 kB/s eta 0:00:00
Collecting mdurl~=0.1 (from markdown-it-py>=2.2.0->rich>=10.11.0->typer<1.0,>=0.12->gradio->-r requirements.txt (line 3))
  Downloading https://pypi.tuna.tsinghua.edu.cn/packages/b3/38/89ba8ad64ae25be8de66a6d463314cf1eb366222074cfda9ee839c56a4b4/mdurl-0.1.2-py3-none-any.whl (10.0 kB)
Installing collected packages: pytz, pydub, websockets, tzdata, typing-extensions, tqdm, tomlkit, sniffio, six, shellingham, semantic-version, ruff, pyyaml, python-multipart, pygments, pillow, packaging, orjson, numpy, mdurl, markupsafe, jiter, h11, fsspec, filelock, ffmpy, exceptiongroup, distro, click, annotated-types, aiofiles, uvicorn, python-dateutil, pydantic-core, markdown-it-py, jinja2, huggingface-hub, httpcore, anyio, starlette, rich, pydantic, pandas, httpx, typer, safehttpx, openai, gradio-client, fastapi, gradio
Successfully installed aiofiles-23.2.1 annotated-types-0.7.0 anyio-4.6.2.post1 click-8.1.7 distro-1.9.0 exceptiongroup-1.2.2 fastapi-0.115.5 ffmpy-0.4.0 filelock-3.16.1 fsspec-2024.10.0 gradio-5.5.0 gradio-client-1.4.2 h11-0.14.0 httpcore-1.0.6 httpx-0.27.2 huggingface-hub-0.26.2 jinja2-3.1.4 jiter-0.7.1 markdown-it-py-3.0.0 markupsafe-2.1.5 mdurl-0.1.2 numpy-2.1.3 openai-1.54.4 orjson-3.10.11 packaging-24.2 pandas-2.2.3 pillow-11.0.0 pydantic-2.9.2 pydantic-core-2.23.4 pydub-0.25.1 pygments-2.18.0 python-dateutil-2.9.0.post0 python-multipart-0.0.12 pytz-2024.2 pyyaml-6.0.2 rich-13.9.4 ruff-0.7.3 safehttpx-0.1.1 semantic-version-2.10.0 shellingham-1.5.4 six-1.16.0 sniffio-1.3.1 starlette-0.41.2 tomlkit-0.12.0 tqdm-4.67.0 typer-0.13.0 typing-extensions-4.12.2 tzdata-2024.2 uvicorn-0.32.0 websockets-12.0
(git-hub-sentinel) 


```