# ZenBook：PDF分层阅读器:用GPT提高十倍阅读速度

ZenBook使用OpenAI的GPT模型来总结PDF文档。它从PDF中提取文本，根据章节分割PDF文件，并对每一章进行总结。进一步的，它可以对每页生成总结，并且你可以直接从页面总结点击跳转到PDF中的对应页。

## 如何使用

1. 克隆这个仓库：
    ```bash
    git clone https://github.com/zenhall/zenbook.git
    ```
2. 进入仓库目录：
    ```bash
    cd zenbook
    ```
3. 安装所需的依赖：
    ```bash
    pip install openai langchain PyPDF2 pypdf Flask tiktoken
    ```
4. 修改api key ：

    在`zenbook.py`文件中，找到`gpt_api_key`变量，将其设置为你的OpenAI的ChatGPT API密钥。
    免费密钥可以从[GPT-API-free](https://github.com/chatanywhere/GPT_API_free)获得。如果要使用openai原生的密钥，需要将`zenbook.py`文件中修改openai.api_base的行注释掉。

5. 放入入pdf文件：

    将你想要总结的PDF文件放入项目中的`book`文件夹，并以英文字母命名。

6. 分割pdf：
    
    首先运行程序
    ```bash
    python zenbook.py
    ```
   在运行程序时，首先输入放入的pdf文件名会，然后选择运行模式，首先要对pdf文件进行分割：
   - 输入1: 手动输入页码数组来分割PDF
   - 输入2: 自动分割PDF（注意：这个模式有可能会出错，如果自动分割失败，请选择手动分割模式）
   
   
   分割完成后，再次运行程序，并选择3模式，进入总结程序。等待总结完成（1min左右），Flask服务器会启动。

7. 运行阅读器：

    Flask服务器启动完成后，打开浏览器，输入`127.0.0.1:5000`来运行网页阅读器。

## 功能

- 提取PDF中的文本
- 根据章节分割PDF
- 对每一章进行总结
- 对每页生成总结
- 从页面总结直接跳转到PDF的对应页

## 依赖

- Python 3.10
- openai
- langchain
- PyPDF2
- Flask

## 贡献

欢迎所有的贡献！如果你有好的想法或者建议，可以创建一个issue或者提交一个pull request。

## 许可

MIT
