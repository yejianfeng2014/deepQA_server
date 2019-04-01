目录结构
 --- chatbot 模型文件部分
 ---chatbot_website 模型发布web 和静态访问ui界面
 ---save 模型存储目录



# deepQA_server
发布模型，单独只使用模型，把模型训练和使用分开

## 安装
`pip3 install -r requirements.txt`):
 * python 3.5
 * tensorflow (tested with v1.0)
 * numpy
 * CUDA (for using GPU) 
 * nltk (natural language toolkit for tokenized the sentences)
 * tqdm (for the nice progression bars)

```
python3 -m nltk.downloader punkt   这个是必须的，在window 不运行就直接报错
```
## web 模块需要安装的内容

channels=1.1.6
django==1.10.7
asgi-redis==1.4.3

redis 需要单独安装然后启动

### Chatbot

main.py 训练模型
main.py --test 这个使用的预训练模型，

main.py --test interactive 采用的是实时对话的模式

python main.py -h 运行帮助模块

    --modelTag <name>: 指定模型名称进行运行
    --keepAll  训练完立刻进行测试

10个单词的上限 ，隐藏层256

### web 模块


复制 训练好的模型  到 `save/model-server/model.ckpt`.(如果没有model-sever 的路径进行创建)

使用这个web框架，第一次需要按照如下配置
```bash
export CHATBOT_SECRET_KEY="my-secret-key" 在window 环境换成 set  CHATBOT_SECRET_KEY="my-secret-key"
cd chatbot_website/
python manage.py makemigrations
python manage.py migrate
```

需要配置 

安装redis 默认端口是6379 如果不是默认地址请修改 
进入这个文件进行修改DeepQA\chatbot_website\chatbot_website\settings.py 


# 自己电脑安装的redise 的地址 

D:\Program Files\Redis



```bash
cd chatbot_website/
redis-server &  # Launch Redis in background
python manage.py runserver
```

http://localhost:8000/ 进行访问 




