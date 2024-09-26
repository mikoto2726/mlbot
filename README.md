# mlbot

# 環境構築
## mlbotというフォルダをwsl上に作成
## mlbotという仮想環境を作成する
pythonの最新バージョンが3.12.6なので 
```
conda create -n mlbot python=3.12.6
```
で作成しようとしたが対応していなかった

conda serch pythonで利用可能なバージョンを確信したところ3.12.5が最新だったので
```
conda create -n mlbot python=3.12.5
```
で作成  

現在の仮想環境を確認
```
~/mlbot > conda info -e                                     py mlbot
# conda environments:
#
base                     /home/iniad/miniconda3
mlbot
```
インストールされているパッケージを確認
```
~/mlbot > conda list                                        py mlbot
# packages in environment at /home/iniad/miniconda3/envs/mlbot:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                        main
_openmp_mutex             5.1                       1_gnu
bzip2                     1.0.8                h5eee18b_6
ca-certificates           2024.7.2             h06a4308_0
expat                     2.6.3                h6a678d5_0
ld_impl_linux-64          2.38                 h1181459_1
libffi                    3.4.4                h6a678d5_1
libgcc-ng                 11.2.0               h1234567_1
libgomp                   11.2.0               h1234567_1
libstdcxx-ng              11.2.0               h1234567_1
libuuid                   1.41.5               h5eee18b_0
ncurses                   6.4                  h6a678d5_0
openssl                   3.0.15               h5eee18b_0
pip                       24.2            py312h06a4308_0
python                    3.12.5               h5148396_1
readline                  8.2                  h5eee18b_0
setuptools                75.1.0          py312h06a4308_0
sqlite                    3.45.3               h5eee18b_0
tk                        8.6.14               h39e8969_0
tzdata                    2024a                h04d1e81_0
wheel                     0.44.0          py312h06a4308_0
xz                        5.4.6                h5eee18b_1
zlib                      1.2.13               h5eee18b_1
```

## jupyter labのインストール
```conda install -c conda-forge jupyterlab```
-c conda-forge は、conda-forge チャンネルからパッケージをインストールするためのオプションです。最新のバージョンやより多くのパッケージが提供されています。

インストールされたパッケージを確認
```
~/mlbot > conda list
# packages in environment at /home/iniad/miniconda3/envs/mlbot:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                 conda_forge    conda-forge
_openmp_mutex             4.5                       2_gnu    conda-forge
anyio                     4.6.0              pyhd8ed1ab_1    conda-forge
argon2-cffi               23.1.0             pyhd8ed1ab_0    conda-forge
argon2-cffi-bindings      21.2.0          py312h5eee18b_0  
arrow                     1.3.0              pyhd8ed1ab_0    conda-forge
asttokens                 2.4.1              pyhd8ed1ab_0    conda-forge
async-lru                 2.0.4              pyhd8ed1ab_0    conda-forge
attrs                     24.2.0             pyh71513ae_0    conda-forge
babel                     2.14.0             pyhd8ed1ab_0    conda-forge
beautifulsoup4            4.12.3             pyha770c72_0    conda-forge
bleach                    6.1.0              pyhd8ed1ab_0    conda-forge
brotli-python             1.0.9           py312h6a678d5_8  
bzip2                     1.0.8                h5eee18b_6  
ca-certificates           2024.8.30            hbcca054_0    conda-forge
cached-property           1.5.2                hd8ed1ab_1    conda-forge
cached_property           1.5.2              pyha770c72_1    conda-forge
certifi                   2024.8.30          pyhd8ed1ab_0    conda-forge
cffi                      1.16.0          py312h5eee18b_1  
charset-normalizer        3.3.2              pyhd8ed1ab_0    conda-forge
comm                      0.2.2              pyhd8ed1ab_0    conda-forge
debugpy                   1.6.7           py312h6a678d5_0  
decorator                 5.1.1              pyhd8ed1ab_0    conda-forge
defusedxml                0.7.1              pyhd8ed1ab_0    conda-forge
entrypoints               0.4                pyhd8ed1ab_0    conda-forge
exceptiongroup            1.2.2              pyhd8ed1ab_0    conda-forge
executing                 2.1.0              pyhd8ed1ab_0    conda-forge
expat                     2.6.3                h6a678d5_0  
fqdn                      1.5.1              pyhd8ed1ab_0    conda-forge
h11                       0.14.0             pyhd8ed1ab_0    conda-forge
h2                        4.1.0              pyhd8ed1ab_0    conda-forge
hpack                     4.0.0              pyh9f0ad1d_0    conda-forge
httpcore                  1.0.5              pyhd8ed1ab_0    conda-forge
httpx                     0.27.2             pyhd8ed1ab_0    conda-forge
hyperframe                6.0.1              pyhd8ed1ab_0    conda-forge
idna                      3.10               pyhd8ed1ab_0    conda-forge
importlib-metadata        8.5.0              pyha770c72_0    conda-forge
importlib_metadata        8.5.0                hd8ed1ab_0    conda-forge
importlib_resources       6.4.5              pyhd8ed1ab_0    conda-forge
ipykernel                 6.29.5             pyh3099207_0    conda-forge
ipython                   8.27.0             pyh707e725_0    conda-forge
isoduration               20.11.0            pyhd8ed1ab_0    conda-forge
jedi                      0.19.1             pyhd8ed1ab_0    conda-forge
jinja2                    3.1.4              pyhd8ed1ab_0    conda-forge
json5                     0.9.25             pyhd8ed1ab_0    conda-forge
jsonpointer               2.0                        py_0    conda-forge
jsonschema                4.23.0             pyhd8ed1ab_0    conda-forge
jsonschema-specifications 2023.12.1          pyhd8ed1ab_0    conda-forge
jsonschema-with-format-nongpl 4.23.0               hd8ed1ab_0    conda-forge
jupyter-lsp               2.2.5              pyhd8ed1ab_0    conda-forge
jupyter_client            8.6.3              pyhd8ed1ab_0    conda-forge
jupyter_core              5.7.2              pyh31011fe_1    conda-forge
jupyter_events            0.10.0             pyhd8ed1ab_0    conda-forge
jupyter_server            2.14.2             pyhd8ed1ab_0    conda-forge
jupyter_server_terminals  0.5.3              pyhd8ed1ab_0    conda-forge
jupyterlab                4.2.5              pyhd8ed1ab_0    conda-forge
jupyterlab_pygments       0.3.0              pyhd8ed1ab_1    conda-forge
jupyterlab_server         2.27.3             pyhd8ed1ab_0    conda-forge
krb5                      1.21.3               h143b758_0  
ld_impl_linux-64          2.38                 h1181459_1  
libedit                   3.1.20230828         h5eee18b_0  
libffi                    3.4.4                h6a678d5_1  
libgcc                    14.1.0               h77fa898_1    conda-forge
libgcc-ng                 14.1.0               h69a702a_1    conda-forge
libgomp                   14.1.0               h77fa898_1    conda-forge
libsodium                 1.0.20               h4ab18f5_0    conda-forge
libstdcxx                 14.1.0               hc0a3c3a_1    conda-forge
libstdcxx-ng              11.2.0               h1234567_1  
libuuid                   1.41.5               h5eee18b_0  
lz4-c                     1.9.4                h6a678d5_1  
markupsafe                2.1.3           py312h5eee18b_0  
matplotlib-inline         0.1.7              pyhd8ed1ab_0    conda-forge
mistune                   3.0.2              pyhd8ed1ab_0    conda-forge
nbclient                  0.10.0             pyhd8ed1ab_0    conda-forge
nbconvert-core            7.16.4             pyhd8ed1ab_1    conda-forge
nbformat                  5.10.4             pyhd8ed1ab_0    conda-forge
ncurses                   6.4                  h6a678d5_0  
nest-asyncio              1.6.0              pyhd8ed1ab_0    conda-forge
notebook-shim             0.2.4              pyhd8ed1ab_0    conda-forge
openssl                   3.3.2                hb9d3cd8_0    conda-forge
overrides                 7.7.0              pyhd8ed1ab_0    conda-forge
packaging                 24.1               pyhd8ed1ab_0    conda-forge
pandocfilters             1.5.0              pyhd8ed1ab_0    conda-forge
parso                     0.8.4              pyhd8ed1ab_0    conda-forge
pexpect                   4.9.0              pyhd8ed1ab_0    conda-forge
pickleshare               0.7.5                   py_1003    conda-forge
pip                       24.2            py312h06a4308_0  
pkgutil-resolve-name      1.3.10             pyhd8ed1ab_1    conda-forge
platformdirs              4.3.6              pyhd8ed1ab_0    conda-forge
prometheus_client         0.21.0             pyhd8ed1ab_0    conda-forge
prompt-toolkit            3.0.47             pyha770c72_0    conda-forge
psutil                    5.9.0           py312h5eee18b_0  
ptyprocess                0.7.0              pyhd3deb0d_0    conda-forge
pure_eval                 0.2.3              pyhd8ed1ab_0    conda-forge
pycparser                 2.22               pyhd8ed1ab_0    conda-forge
pygments                  2.18.0             pyhd8ed1ab_0    conda-forge
pysocks                   1.7.1              pyha2e5f31_6    conda-forge
python                    3.12.5               h5148396_1  
python-dateutil           2.9.0              pyhd8ed1ab_0    conda-forge
python-fastjsonschema     2.20.0             pyhd8ed1ab_0    conda-forge
python-json-logger        2.0.7              pyhd8ed1ab_0    conda-forge
pytz                      2024.2             pyhd8ed1ab_0    conda-forge
pyyaml                    6.0.1           py312h5eee18b_0  
pyzmq                     25.1.2          py312h6a678d5_0  
readline                  8.2                  h5eee18b_0  
referencing               0.35.1             pyhd8ed1ab_0    conda-forge
requests                  2.32.3             pyhd8ed1ab_0    conda-forge
rfc3339-validator         0.1.4              pyhd8ed1ab_0    conda-forge
rfc3986-validator         0.1.1              pyh9f0ad1d_0    conda-forge
rpds-py                   0.10.6          py312hb02cf49_0  
send2trash                1.8.3              pyh0d859eb_0    conda-forge
setuptools                75.1.0          py312h06a4308_0  
six                       1.16.0             pyh6c4a22f_0    conda-forge
sniffio                   1.3.1              pyhd8ed1ab_0    conda-forge
soupsieve                 2.5                pyhd8ed1ab_1    conda-forge
sqlite                    3.45.3               h5eee18b_0  
stack_data                0.6.2              pyhd8ed1ab_0    conda-forge
terminado                 0.18.1             pyh0d859eb_0    conda-forge
tinycss2                  1.3.0              pyhd8ed1ab_0    conda-forge
tk                        8.6.14               h39e8969_0  
tomli                     2.0.1              pyhd8ed1ab_0    conda-forge
tornado                   6.4.1           py312h5eee18b_0  
traitlets                 5.14.3             pyhd8ed1ab_0    conda-forge
types-python-dateutil     2.9.0.20240906     pyhd8ed1ab_0    conda-forge
typing-extensions         4.12.2               hd8ed1ab_0    conda-forge
typing_extensions         4.12.2             pyha770c72_0    conda-forge
typing_utils              0.1.0              pyhd8ed1ab_0    conda-forge
tzdata                    2024a                h04d1e81_0  
uri-template              1.3.0              pyhd8ed1ab_0    conda-forge
urllib3                   2.2.3              pyhd8ed1ab_0    conda-forge
wcwidth                   0.2.13             pyhd8ed1ab_0    conda-forge
webcolors                 24.8.0             pyhd8ed1ab_0    conda-forge
webencodings              0.5.1              pyhd8ed1ab_2    conda-forge
websocket-client          1.8.0              pyhd8ed1ab_0    conda-forge
wheel                     0.44.0          py312h06a4308_0  
xz                        5.4.6                h5eee18b_1  
yaml                      0.2.5                h7f98852_2    conda-forge
zeromq                    4.3.5                ha4adb4c_5    conda-forge
zipp                      3.20.2             pyhd8ed1ab_0    conda-forge
zlib                      1.2.13               h5eee18b_1  
zstandard                 0.22.0          py312h2c38b39_0  
zstd                      1.5.5                hc292b87_2  
```
jupyter labのバージョンを確認
```
~/mlbot > jupyter lab --version                             py mlbot
4.2.5
```

jupyter labを起動した際にエラーが発生
```
Library libsecret-1.so.0 cannot be loaded, related functionality will not be available

(tilix:4543): GLib-GObject-WARNING **: 15:17:07.712: invalid (NULL) pointer instance

(tilix:4543): GLib-GObject-CRITICAL **: 15:17:07.712: g_signal_handlers_disconnect_matched: assertion 'G_TYPE_CHECK_INSTANCE (instance)' failed

[I 2024-09-25 15:17:08.503 ServerApp] Skipped non-installed server(s): bash-language-server, dockerfile-language-server-nodejs, ...
```
これらのエラーは、主にシステムに必要なライブラリや依存関係が不足していることが原因で発生しています。

```
~/mlbot > jupyter lab
```
これで起動できるようになりました
Ctrl+Cで終了

機械学習に必要なライブラリをインストール
requirements.txtを用意
```
numpy
pandas
scikit-learn
matplotlib
seaborn
tensorflow
keras
torch
torchvision
xgboost
lightgbm
statsmodels
jupyterlab
scipy
torch
ccxt
```
requirements.txtを用いてインストール
```
~/mlbot > pip install -r requirements.txt
```
インストール後のパッケージ
```
~/mlbot > conda list                                   1m 32s py mlbot
# packages in environment at /home/iniad/miniconda3/envs/mlbot:
#
# Name                    Version                   Build  Channel
_libgcc_mutex             0.1                 conda_forge    conda-forge
_openmp_mutex             4.5                       2_gnu    conda-forge
absl-py                   2.1.0                    pypi_0    pypi
aiodns                    3.2.0                    pypi_0    pypi
aiohappyeyeballs          2.4.0                    pypi_0    pypi
aiohttp                   3.10.6                   pypi_0    pypi
aiosignal                 1.3.1                    pypi_0    pypi
anyio                     4.6.0              pyhd8ed1ab_1    conda-forge
argon2-cffi               23.1.0             pyhd8ed1ab_0    conda-forge
argon2-cffi-bindings      21.2.0          py312h5eee18b_0
arrow                     1.3.0              pyhd8ed1ab_0    conda-forge
asttokens                 2.4.1              pyhd8ed1ab_0    conda-forge
astunparse                1.6.3                    pypi_0    pypi
async-lru                 2.0.4              pyhd8ed1ab_0    conda-forge
attrs                     24.2.0             pyh71513ae_0    conda-forge
babel                     2.14.0             pyhd8ed1ab_0    conda-forge
beautifulsoup4            4.12.3             pyha770c72_0    conda-forge
bleach                    6.1.0              pyhd8ed1ab_0    conda-forge
brotli-python             1.0.9           py312h6a678d5_8
bzip2                     1.0.8                h5eee18b_6
ca-certificates           2024.8.30            hbcca054_0    conda-forge
cached-property           1.5.2                hd8ed1ab_1    conda-forge
cached_property           1.5.2              pyha770c72_1    conda-forge
ccxt                      4.4.7                    pypi_0    pypi
certifi                   2024.8.30          pyhd8ed1ab_0    conda-forge
cffi                      1.16.0          py312h5eee18b_1
chainer                   7.8.1                    pypi_0    pypi
charset-normalizer        3.3.2              pyhd8ed1ab_0    conda-forge
comm                      0.2.2              pyhd8ed1ab_0    conda-forge
contourpy                 1.3.0                    pypi_0    pypi
cryptography              43.0.1                   pypi_0    pypi
cycler                    0.12.1                   pypi_0    pypi
debugpy                   1.6.7           py312h6a678d5_0
decorator                 5.1.1              pyhd8ed1ab_0    conda-forge
defusedxml                0.7.1              pyhd8ed1ab_0    conda-forge
entrypoints               0.4                pyhd8ed1ab_0    conda-forge
exceptiongroup            1.2.2              pyhd8ed1ab_0    conda-forge
executing                 2.1.0              pyhd8ed1ab_0    conda-forge
expat                     2.6.3                h6a678d5_0
filelock                  3.16.1                   pypi_0    pypi
flatbuffers               24.3.25                  pypi_0    pypi
fonttools                 4.54.1                   pypi_0    pypi
fqdn                      1.5.1              pyhd8ed1ab_0    conda-forge
frozenlist                1.4.1                    pypi_0    pypi
fsspec                    2024.9.0                 pypi_0    pypi
gast                      0.6.0                    pypi_0    pypi
google-pasta              0.2.0                    pypi_0    pypi
grpcio                    1.66.1                   pypi_0    pypi
h11                       0.14.0             pyhd8ed1ab_0    conda-forge
h2                        4.1.0              pyhd8ed1ab_0    conda-forge
h5py                      3.11.0                   pypi_0    pypi
hpack                     4.0.0              pyh9f0ad1d_0    conda-forge
httpcore                  1.0.5              pyhd8ed1ab_0    conda-forge
httpx                     0.27.2             pyhd8ed1ab_0    conda-forge
hyperframe                6.0.1              pyhd8ed1ab_0    conda-forge
idna                      3.10               pyhd8ed1ab_0    conda-forge
importlib-metadata        8.5.0              pyha770c72_0    conda-forge
importlib_metadata        8.5.0                hd8ed1ab_0    conda-forge
importlib_resources       6.4.5              pyhd8ed1ab_0    conda-forge
ipykernel                 6.29.5             pyh3099207_0    conda-forge
ipython                   8.27.0             pyh707e725_0    conda-forge
isoduration               20.11.0            pyhd8ed1ab_0    conda-forge
jaraco-classes            3.4.0                    pypi_0    pypi
jaraco-context            6.0.1                    pypi_0    pypi
jaraco-functools          4.0.2                    pypi_0    pypi
jedi                      0.19.1             pyhd8ed1ab_0    conda-forge
jeepney                   0.8.0                    pypi_0    pypi
jinja2                    3.1.4              pyhd8ed1ab_0    conda-forge
joblib                    1.4.2                    pypi_0    pypi
json5                     0.9.25             pyhd8ed1ab_0    conda-forge
jsonpointer               2.0                        py_0    conda-forge
jsonschema                4.23.0             pyhd8ed1ab_0    conda-forge
jsonschema-specifications 2023.12.1          pyhd8ed1ab_0    conda-forge
jsonschema-with-format-nongpl 4.23.0               hd8ed1ab_0    conda-forge
jupyter-lsp               2.2.5              pyhd8ed1ab_0    conda-forge
jupyter_client            8.6.3              pyhd8ed1ab_0    conda-forge
jupyter_core              5.7.2              pyh31011fe_1    conda-forge
jupyter_events            0.10.0             pyhd8ed1ab_0    conda-forge
jupyter_server            2.14.2             pyhd8ed1ab_0    conda-forge
jupyter_server_terminals  0.5.3              pyhd8ed1ab_0    conda-forge
jupyterlab                4.2.5              pyhd8ed1ab_0    conda-forge
jupyterlab_pygments       0.3.0              pyhd8ed1ab_1    conda-forge
jupyterlab_server         2.27.3             pyhd8ed1ab_0    conda-forge
keras                     3.5.0                    pypi_0    pypi
keyring                   25.4.1                   pypi_0    pypi
kiwisolver                1.4.7                    pypi_0    pypi
krb5                      1.21.3               h143b758_0
ld_impl_linux-64          2.38                 h1181459_1
libclang                  18.1.1                   pypi_0    pypi
libedit                   3.1.20230828         h5eee18b_0
libffi                    3.4.4                h6a678d5_1
libgcc                    14.1.0               h77fa898_1    conda-forge
libgcc-ng                 14.1.0               h69a702a_1    conda-forge
libgomp                   14.1.0               h77fa898_1    conda-forge
libsodium                 1.0.20               h4ab18f5_0    conda-forge
libstdcxx                 14.1.0               hc0a3c3a_1    conda-forge
libstdcxx-ng              11.2.0               h1234567_1
libuuid                   1.41.5               h5eee18b_0
lightgbm                  4.5.0                    pypi_0    pypi
lz4-c                     1.9.4                h6a678d5_1
markdown                  3.7                      pypi_0    pypi
markdown-it-py            3.0.0                    pypi_0    pypi
markupsafe                2.1.3           py312h5eee18b_0
matplotlib                3.9.2                    pypi_0    pypi
matplotlib-inline         0.1.7              pyhd8ed1ab_0    conda-forge
mdurl                     0.1.2                    pypi_0    pypi
mistune                   3.0.2              pyhd8ed1ab_0    conda-forge
ml-dtypes                 0.4.1                    pypi_0    pypi
more-itertools            10.5.0                   pypi_0    pypi
mpmath                    1.3.0                    pypi_0    pypi
multidict                 6.1.0                    pypi_0    pypi
namex                     0.0.8                    pypi_0    pypi
nbclient                  0.10.0             pyhd8ed1ab_0    conda-forge
nbconvert-core            7.16.4             pyhd8ed1ab_1    conda-forge
nbformat                  5.10.4             pyhd8ed1ab_0    conda-forge
ncurses                   6.4                  h6a678d5_0
nest-asyncio              1.6.0              pyhd8ed1ab_0    conda-forge
networkx                  3.3                      pypi_0    pypi
notebook-shim             0.2.4              pyhd8ed1ab_0    conda-forge
numpy                     1.26.4                   pypi_0    pypi
nvidia-cublas-cu12        12.1.3.1                 pypi_0    pypi
nvidia-cuda-cupti-cu12    12.1.105                 pypi_0    pypi
nvidia-cuda-nvrtc-cu12    12.1.105                 pypi_0    pypi
nvidia-cuda-runtime-cu12  12.1.105                 pypi_0    pypi
nvidia-cudnn-cu12         9.1.0.70                 pypi_0    pypi
nvidia-cufft-cu12         11.0.2.54                pypi_0    pypi
nvidia-curand-cu12        10.3.2.106               pypi_0    pypi
nvidia-cusolver-cu12      11.4.5.107               pypi_0    pypi
nvidia-cusparse-cu12      12.1.0.106               pypi_0    pypi
nvidia-nccl-cu12          2.20.5                   pypi_0    pypi
nvidia-nvjitlink-cu12     12.6.68                  pypi_0    pypi
nvidia-nvtx-cu12          12.1.105                 pypi_0    pypi
openssl                   3.3.2                hb9d3cd8_0    conda-forge
opt-einsum                3.3.0                    pypi_0    pypi
optree                    0.12.1                   pypi_0    pypi
overrides                 7.7.0              pyhd8ed1ab_0    conda-forge
packaging                 24.1               pyhd8ed1ab_0    conda-forge
pandas                    2.2.3                    pypi_0    pypi
pandocfilters             1.5.0              pyhd8ed1ab_0    conda-forge
parso                     0.8.4              pyhd8ed1ab_0    conda-forge
patsy                     0.5.6                    pypi_0    pypi
pexpect                   4.9.0              pyhd8ed1ab_0    conda-forge
pickleshare               0.7.5                   py_1003    conda-forge
pillow                    10.4.0                   pypi_0    pypi
pip                       24.2            py312h06a4308_0
pkgutil-resolve-name      1.3.10             pyhd8ed1ab_1    conda-forge
platformdirs              4.3.6              pyhd8ed1ab_0    conda-forge
prometheus_client         0.21.0             pyhd8ed1ab_0    conda-forge
prompt-toolkit            3.0.47             pyha770c72_0    conda-forge
protobuf                  4.25.5                   pypi_0    pypi
psutil                    5.9.0           py312h5eee18b_0
ptyprocess                0.7.0              pyhd3deb0d_0    conda-forge
pure_eval                 0.2.3              pyhd8ed1ab_0    conda-forge
pycares                   4.4.0                    pypi_0    pypi
pycparser                 2.22               pyhd8ed1ab_0    conda-forge
pygments                  2.18.0             pyhd8ed1ab_0    conda-forge
pyparsing                 3.1.4                    pypi_0    pypi
pysocks                   1.7.1              pyha2e5f31_6    conda-forge
python                    3.12.5               h5148396_1
python-dateutil           2.9.0              pyhd8ed1ab_0    conda-forge
python-fastjsonschema     2.20.0             pyhd8ed1ab_0    conda-forge
python-json-logger        2.0.7              pyhd8ed1ab_0    conda-forge
pytz                      2024.2             pyhd8ed1ab_0    conda-forge
pyyaml                    6.0.1           py312h5eee18b_0
pyzmq                     25.1.2          py312h6a678d5_0
readline                  8.2                  h5eee18b_0
referencing               0.35.1             pyhd8ed1ab_0    conda-forge
requests                  2.32.3             pyhd8ed1ab_0    conda-forge
rfc3339-validator         0.1.4              pyhd8ed1ab_0    conda-forge
rfc3986-validator         0.1.1              pyh9f0ad1d_0    conda-forge
rich                      13.8.1                   pypi_0    pypi
rpds-py                   0.10.6          py312hb02cf49_0
scikit-learn              1.5.2                    pypi_0    pypi
scipy                     1.14.1                   pypi_0    pypi
seaborn                   0.13.2                   pypi_0    pypi
secretstorage             3.3.3                    pypi_0    pypi
send2trash                1.8.3              pyh0d859eb_0    conda-forge
setuptools                75.1.0          py312h06a4308_0
six                       1.16.0             pyh6c4a22f_0    conda-forge
sniffio                   1.3.1              pyhd8ed1ab_0    conda-forge
soupsieve                 2.5                pyhd8ed1ab_1    conda-forge
sqlite                    3.45.3               h5eee18b_0
stack_data                0.6.2              pyhd8ed1ab_0    conda-forge
statsmodels               0.14.3                   pypi_0    pypi
sympy                     1.13.3                   pypi_0    pypi
tensorboard               2.17.1                   pypi_0    pypi
tensorboard-data-server   0.7.2                    pypi_0    pypi
tensorflow                2.17.0                   pypi_0    pypi
termcolor                 2.4.0                    pypi_0    pypi
terminado                 0.18.1             pyh0d859eb_0    conda-forge
threadpoolctl             3.5.0                    pypi_0    pypi
tinycss2                  1.3.0              pyhd8ed1ab_0    conda-forge
tk                        8.6.14               h39e8969_0
tomli                     2.0.1              pyhd8ed1ab_0    conda-forge
torch                     2.4.1                    pypi_0    pypi
torchvision               0.19.1                   pypi_0    pypi
tornado                   6.4.1           py312h5eee18b_0
traitlets                 5.14.3             pyhd8ed1ab_0    conda-forge
triton                    3.0.0                    pypi_0    pypi
types-python-dateutil     2.9.0.20240906     pyhd8ed1ab_0    conda-forge
typing-extensions         4.12.2               hd8ed1ab_0    conda-forge
typing_extensions         4.12.2             pyha770c72_0    conda-forge
typing_utils              0.1.0              pyhd8ed1ab_0    conda-forge
tzdata                    2024.2                   pypi_0    pypi
uri-template              1.3.0              pyhd8ed1ab_0    conda-forge
urllib3                   2.2.3              pyhd8ed1ab_0    conda-forge
wcwidth                   0.2.13             pyhd8ed1ab_0    conda-forge
webcolors                 24.8.0             pyhd8ed1ab_0    conda-forge
webencodings              0.5.1              pyhd8ed1ab_2    conda-forge
websocket-client          1.8.0              pyhd8ed1ab_0    conda-forge
werkzeug                  3.0.4                    pypi_0    pypi
wheel                     0.44.0          py312h06a4308_0
wrapt                     1.16.0                   pypi_0    pypi
xgboost                   2.1.1                    pypi_0    pypi
xz                        5.4.6                h5eee18b_1
yaml                      0.2.5                h7f98852_2    conda-forge
yarl                      1.12.1                   pypi_0    pypi
zeromq                    4.3.5                ha4adb4c_5    conda-forge
zipp                      3.20.2             pyhd8ed1ab_0    conda-forge
zlib                      1.2.13               h5eee18b_1
zstandard                 0.22.0          py312h2c38b39_0
zstd                      1.5.5                hc292b87_2
```
jupyter labを起動
```
jupyter lab
```
新しくファイルを作成してコードを書いていく
## import
```
# 数値計算とデータ操作
import numpy as np
import pandas as pd

# 機械学習
from sklearn import datasets, preprocessing, model_selection, metrics
import xgboost as xgb
import lightgbm as lgb
import tensorflow as tf
from tensorflow import keras
import torch
import torchvision

# 統計モデリング
import statsmodels.api as sm

# データ可視化
import matplotlib.pyplot as plt
import seaborn as sns
import sweetviz as sv
from autoviz.AutoViz_Class import AutoViz_Class

# 科学計算
import scipy

# 金融データの取得
import ccxt

#データ収集用
from datetime import datetime, timedelta

# 非機械学習バックテスト用のコート
import backtrader as bt
from matplotlib import style
```

## データ収集
```
# Binanceのインスタンスを作成
exchange = ccxt.binance()

# BTC/USDTのデータを取得
symbol = 'BTC/USDT'
timeframe = '1h'  # 1時間足のデータ
since = exchange.parse8601('2018-01-01T00:00:00Z')  # データの開始日

# データを取得する関数
def fetch_all_ohlcv(symbol, timeframe, since):
    all_ohlcv = []
    now = exchange.milliseconds()
    while since < now:
        try:
            ohlcv = exchange.fetch_ohlcv(symbol, timeframe, since)
            if not ohlcv:
                break
            since = ohlcv[-1][0] + 1  # タイムスタンプを更新
            all_ohlcv.extend(ohlcv)
        except Exception as e:
            print(f'An error occurred: {e}')
            break
    return all_ohlcv

# データを取得
ohlcv = fetch_all_ohlcv(symbol, timeframe, since)
data = pd.DataFrame(ohlcv, columns=['timestamp', 'open', 'high', 'low', 'close', 'volume'])

# タイムスタンプを変換
data['timestamp'] = pd.to_datetime(data['timestamp'], unit='ms')

# CSVファイルとして保存
data.to_csv('btc_usdt_1h_2018_to_now.csv', index=False)

print('Data fetching and saving completed.')
```

データの読み込み
```
df = pd.read_csv("btc_usdt_1h_2018_to_now.csv")
```

可視化
```
# レポートの生成
report = sv.analyze(df)
report.show_notebook()
```

```
# 'close' 列をターゲット変数としてレポートを生成
report = sv.analyze(df, target_feat='close')
report.show_notebook()
```

```
AV = AutoViz_Class()
# 可視化の実行
df_viz = AV.AutoViz(
    filename="",               # ファイル名は空文字に設定（df を直接使用するため）
    sep=",",                   # データの区切り文字（通常はカンマ）
    depVar="",                 # 目的変数（ターゲット変数）の列名を指定（なければ空文字）
    dfte=df,                   # データフレームを直接指定
    header=0,                  # ヘッダーの行番号（通常は0）
    verbose=1,                 # 詳細な出力を表示
    lowess=False,              # Lowess 曲線を使用するか
    chart_format="svg",        # チャートの形式（svg, png など）
    max_rows_analyzed=150000,  # 分析する最大行数
    max_cols_analyzed=30,      # 分析する最大列数
    save_plot_dir=None         # プロットを保存するディレクトリ（None の場合は保存しない）
)
%matplotlib inline
```

```
# 目的変数を指定して可視化を実行
df_viz = AV.AutoViz(
    filename="",
    sep=",",
    depVar="close",  # 目的変数を指定
    dfte=df,
    header=0,
    verbose=1,
    lowess=False,
    chart_format="svg",
    max_rows_analyzed=150000,
    max_cols_analyzed=30,
    save_plot_dir=None
)
%matplotlib inline
```

非機械学習のバックテスト
```
# CSVファイルを読み込む
data = pd.read_csv('btc_usdt_1h_2018_to_now.csv', parse_dates=['timestamp'])

# Backtrader用のデータフォーマットに変換
class PandasData(bt.feeds.PandasData):
    params = (
        ('datetime', 'timestamp'),
        ('open', 'open'),
        ('high', 'high'),
        ('low', 'low'),
        ('close', 'close'),
        ('volume', 'volume'),
    )

data_feed = PandasData(dataname=data)

# 反転したストラテジー
class ReversedSMACrossStrategy(bt.Strategy):
    params = (
        ('sma_short_period', 50),
        ('sma_long_period', 200),
        ('trade_size', 0.03),  # 取引サイズ
        ('stop_loss', 0.02),  # 2%のストップロス
        ('take_profit', 0.04)  # 4%のテイクプロフィット
    )

    def __init__(self):
        self.sma_short = bt.indicators.SimpleMovingAverage(self.data.close, period=self.params.sma_short_period)
        self.sma_long = bt.indicators.SimpleMovingAverage(self.data.close, period=self.params.sma_long_period)
        self.bbands = bt.indicators.BollingerBands(self.data.close)
        self.portfolio_value = []
        self.trade_count = 0

    def log(self, txt, dt=None):
        ''' 日付付きでログを出力 '''
        dt = dt or self.datas[0].datetime.date(0)
        print(f'{dt.isoformat()} {txt}')

    def next(self):
        self.portfolio_value.append(self.broker.getvalue())  # ポートフォリオ値を記録

        # 反転したSMAクロスオーバーとボリンジャーバンドの組み合わせ
        if self.sma_short < self.sma_long:  # 下降トレンド（反転）
            if not self.position:
                if self.data.close > self.bbands.top:
                    self.buy(size=self.params.trade_size)  # 購入
                    self.trade_count += 1
                    self.log(f'BUY CREATE, {self.data.close[0]:.2f}')
            elif self.position.size > 0:
                if self.data.close < self.bbands.bot:
                    self.sell(size=self.params.trade_size)  # ポジションを閉じる
                    self.trade_count += 1
                    self.log(f'SELL CREATE, {self.data.close[0]:.2f}')
        elif self.sma_short > self.sma_long:  # 上昇トレンド（反転）
            if not self.position:
                if self.data.close < self.bbands.bot:
                    self.sell(size=self.params.trade_size)  # 売却
                    self.trade_count += 1
                    self.log(f'SELL CREATE, {self.data.close[0]:.2f}')
            elif self.position.size < 0:
                if self.data.close > self.bbands.top:
                    self.buy(size=self.params.trade_size)  # ポジションを閉じる
                    self.trade_count += 1
                    self.log(f'BUY CREATE, {self.data.close[0]:.2f}')

        # ストップロスとテイクプロフィットの設定
        for order in self.broker.orders:
            if order.status == order.Accepted:
                if order.isbuy():
                    sl_price = order.executed.price * (1 - self.params.stop_loss)
                    tp_price = order.executed.price * (1 + self.params.take_profit)
                    self.sell(size=order.size, exectype=bt.Order.Stop, price=sl_price)
                    self.sell(size=order.size, exectype=bt.Order.Limit, price=tp_price)
                elif order.issell():
                    sl_price = order.executed.price * (1 + self.params.stop_loss)
                    tp_price = order.executed.price * (1 - self.params.take_profit)
                    self.buy(size=order.size, exectype=bt.Order.Stop, price=sl_price)
                    self.buy(size=order.size, exectype=bt.Order.Limit, price=tp_price)

# バックテストの実行
if __name__ == '__main__':
    cerebro = bt.Cerebro()
    cerebro.adddata(data_feed)
    cerebro.addstrategy(ReversedSMACrossStrategy)
    initial_cash = 10000  # 初期資金
    cerebro.broker.setcash(initial_cash)

    # 手数料の設定
    cerebro.broker.setcommission(commission=0.001)  # 0.1%の手数料

    print('Starting Portfolio Value: %.2f' % cerebro.broker.getvalue())
    result = cerebro.run()
    final_value = cerebro.broker.getvalue()
    print('Final Portfolio Value: %.2f' % final_value)

    # ROIの計算
    roi = ((final_value - initial_cash) / initial_cash) * 100
    print(f'ROI: {roi:.2f}%')

    # 取引回数と一日の平均取引回数の計算
    strategy = result[0]
    trade_count = strategy.trade_count
    total_days = (data['timestamp'].iloc[-1] - data['timestamp'].iloc[0]).days
    avg_trades_per_day = trade_count / total_days
    print(f'Total Trades: {trade_count}')
    print(f'Average Trades Per Day: {avg_trades_per_day:.2f}')

    # グラフのカスタマイズ
    style.use('ggplot')
    
    # 損益グラフをプロット
    portfolio_values = strategy.portfolio_value
    dates = data['timestamp'][:len(portfolio_values)]
    
    fig, ax = plt.subplots(figsize=(12, 8))
    ax.plot(dates, portfolio_values, label='Portfolio Value')
    ax.set_title('Portfolio Value Over Time')
    ax.set_xlabel('Date')
    ax.set_ylabel('Portfolio Value (USD)')
    ax.legend()
    ax.grid(True)
    
    plt.show()
```
