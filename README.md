# 智能音箱控制APP

| 发布日期 | 2019年12月16日 | 
| ------ | ------ | 
| 产品名称 | 智能音箱控制APP | 
| 文件现状 | 正在更新 | 
| 文件的主人 | 胡铖怡 | 
| 设计师 | 胡铖怡 |
| 开发者 | 胡铖怡 |
| 迭代版本 | 1.0 |

# PRD价值主张设计
## PRD1.加值宣言
随着人工智能的发展，智能音箱走进了越来越多的家庭，但现在市面上的智能音箱的功能都还停留在基础的语音唤醒及语音识别。基于现状，现将在讯飞的声纹识别API基础上运用百度的对话情绪识别API，对现有产品进行加值和优化，让产品懂你更懂情绪。主要：运用讯飞的远场唤醒API，清除扬声器本身的声音，其次运用讯飞的声纹识别API，识别用户个体，为其推荐喜欢的歌曲；将用户输入的语音用百度的短语音识别API转换为文本再运用百度的对话情绪识别API识别到用户的情绪并推荐符合当下心境的歌曲，提高用户体验。

## PRD2.核心价值 （最小可行性产品）
#### 着眼于当下智能音箱产品使其优化，可以针对用户个体及用户的情绪提供更精准的歌曲推送，提升用户体验。
- 针对性 :针对识别的用户个体推荐其喜欢的歌曲
- 智能化 ：根据用户语音输入的内容文本识别用户当下情绪，推荐符合心情的歌曲

## PRD3.核心价值与用户痛点 
1. 用户痛点宣言：
    - 帮助用户获得更加符合个人爱好及当下心情的歌曲推荐。解决需要手动选歌难和选歌久的问题。
2. 用户痛点场景：
    - 儿子想在洗澡的时候听歌，无奈打开音箱继续播放是爸爸爱听的歌。
    - 爸爸下班后很疲惫，想用最简单的交互方法听到自己平常爱听的歌，回到家却要手动选歌连接音箱播放。
    - 妈妈做饭的时候喜欢听歌，今天女儿放假回家吃饭，妈妈特别愉快，想在做饭的时候听到欢快的歌曲。

## PRD4.人工智能概率性与用户痛点    
这里主要关注1.讯飞声纹识别API和3.百度文本情绪识别API
### 用户痛点1：需要手动选择个人喜欢的歌曲     
解决痛点1的AI及概率性考量：
 - 1.[讯飞声纹识别API](https://www.xfyun.cn/services/isv)可以将说话人声纹信息与库中的已知用户声纹进行1:1比对验证和1:N的检索，并且还需要将说话人所读出的数字声音与云端动态给定的数字内容进行验证。最终，仅当声纹+内容都匹配即验证/检索成功
### 用户痛点2：现在情绪不高，产品却给我推荐平常听过的很愉快的歌曲，不符合当下的心情。    
解决用户痛点2的AI及概率性考量:
-  2.[百度短语音识别](https://ai.baidu.com/tech/speech/asr)完成人机交互的部分
 略带口音的普通话、粤语四川话方言、英文，均可有效识别。但对口音浓厚、生僻字有一定障碍。
 融合百度自然语言处理技术，近场中文普通话识别准确率达98% 
-  3.[百度文本情绪识别](https://ai.baidu.com/tech/nlp_apply/emotion_detection)      
 - ![image](https://github.com/Huhu-Estelle/API-/blob/master/%E6%83%85%E7%BB%AA%E5%88%86%E7%B1%BB.png)                识别情绪分为两级。一级情绪分为正向、中性、负向3种，正向情绪细分为：喜爱、愉快、感谢3种；负向情绪细分为：抱怨、愤怒、厌恶、恐惧、悲伤5种 。      
 缺点是：文本中需要给出明显的形容词，才能帮助情绪识别的细化。而语言中的隐藏情绪不能被有效识别。      
 例如：       
 - ![image](https://github.com/Huhu-Estelle/API-/blob/master/%E6%83%85%E7%BB%AA%E8%AF%86%E5%88%AB1.jpg)
 出现了“累”这个关键词，识别得出情绪是疲惫
 - ![image](https://github.com/Huhu-Estelle/API-/blob/master/%E6%83%85%E7%BB%AA%E8%AF%86%E5%88%AB2.jpg)
 并没有识别出语境下的隐喻的可能性
             
## PRD5.需求列表与人工智能API加值
需求列表：使用人工智能的加值是否反映到需求列表（核心功能的排序上）且PRD列出明显有可行及可用的API

| 用户痛点 | API加值 | 重要程度 |
| ------ | ------ | ------ |
| 想播放自己喜欢的歌曲需要手动选择 | 声纹识别API | 重要 
| 用户很疲惫需要手动选择符合心情的歌曲 | 文本情绪识别API | 重要 
| 用户需要手动进行一切操作 | 段语音识别API | 较为重要 

# 原型
## 原型1.交互及界面设计 
## 1.首页
![image](https://github.com/Huhu-Estelle/API-/blob/master/%E9%A6%96%E9%A1%B5.png)
## 2.添加声纹-- 讯飞声纹识别API
![image](https://github.com/Huhu-Estelle/API-/blob/master/%E6%B7%BB%E5%8A%A0%E5%A3%B0%E7%BA%B9.png)
## 3.声纹识别和情绪识别
![image](https://github.com/Huhu-Estelle/API-/blob/master/%E5%A3%B0%E7%BA%B9%E8%AF%86%E5%88%AB%E5%92%8C%E6%83%85%E7%BB%AA%E8%AF%86%E5%88%AB.png)
## 原型2.信息设计 5%
## API使用流程图--帮助用户场景和途径理解
![image](https://github.com/Huhu-Estelle/API-/blob/master/API%E5%9C%BA%E6%99%AF%E6%B5%81%E7%A8%8B%E5%9B%BE.png)
## 原型3.原型文档 5%
[原型原型](http://nfunm022.gitee.io/api)

## 原型4.口头操作说明 5%
- 1.在【首页】，实现设备蓝牙连接；
- 2.【听歌】界面，用户只需语音输入口令，根据声波，APP通过讯飞声纹识别API判断该声纹与哪位用户的声音匹配，根据其平常曲风推荐歌曲；
- 3.用户输入的语音内容中，通过百度短语音识别API将语音转文字，百度文本情绪识别API识别该用户对自己的情绪较清晰的描述，推荐适合该用户当下的心情适合听的歌。
- 4.若要添加新用户的声API 产品使用关键AI或机器学习之API的输出入展示 1纹信息，在【我的】界面，根据提示信息朗读显示的数字就可以添加该声纹至语音库。

# API 产品使用关键AI或机器学习之API的输出入展示 
## API1.使用水平
## 1.声纹识别API输入
代码示例：
```
from aip import AipSpeech

APP_ID = '15180100'
API_KEY = '4Lls6ixvcoB7lmacnLNKmH8f'
SECRET_KEY = 'LBlvF01tGMU6Bir2Vb4wjUXBwZCDXyws'

client = AipSpeech(APP_ID, API_KEY, SECRET_KEY)

# 读取文件
def get_file_content(filePath):
    with open(filePath, 'rb') as fp:
        return fp.read()

# 识别本地文件
client.asr(get_file_content('代码示例1.pcm'), 'pcm', 16000, {
    'dev_pid': 1536,
})
```

## 声纹识别API输出
```
{
    "err_no": 0,
    "err_msg": "success.",
    "corpus_no": "15984125203278346378",
    "sn": "235C524F-23TR-562F-73DR-9157WOMR2A2H",
    "result": ["用户1"]
}
```
## 2.对话情绪识别API输入
```
from aip import AipSpeech

APP_ID = '15180100'
API_KEY = '4Lls6ixvcoB7lmacnLNKmH8f'
SECRET_KEY = 'LBlvF01tGMU6Bir2Vb4wjUXBwZCDXyws'

client = AipSpeech(APP_ID, API_KEY, SECRET_KEY)

# 读取文件
def get_emotion(content):
    token=get_token()
    url = 'https://aip.baidubce.com/rpc/2.0/nlp/v1/emotion'
    params = dict()
    params['scene'] = 'talk'
    params['text'] = content
    params = json.dumps(params).encode('utf-8')
    access_token = token
    url = url + "?access_token=" + access_token
    url = url + "&charset=UTF-8"
    request = urllib.request.Request(url=url, data=params)
    request.add_header('Content-Type', 'application/json')
    response = urllib.request.urlopen(request)
    content = response.read()
    if content:
        content=content.decode('utf-8')
        data = json.loads(content)
        return data
    else:
        return ''
    print (get_emotion('本来今天高高兴兴'))
```
## 对话情绪识别API输出
```
{'log_id': 8567920447474187651, 'text': '本来今天高高兴兴', 'items': [{'subitems': [{'prob': 0.501008, 'label': 'happy'}], 'replies': ['笑一笑十年少'], 'prob': 0.501008, 'label': 'optimistic'}, {'subitems': [], 'replies': [], 'prob': 0.49872, 'label': 'neutral'}, {'subitems': [], 'replies': [], 'prob': 0.000272128, 'label': 'pessimistic'}]}

```
## API2.使用比较分析
- 百度语音API能够摆脱生僻字和拼音障碍，将所输入文字，直接用语音的方式输入，并且有着百度输入法和魅族输入法的合作案例。
- 讯飞语音API有着连续短语音转文字服务；支持方言语音输入。
- 讯飞、微软平台暂无对话情绪识别API
## API3.使用后风险报告
- 1.语音识别、合成接口调用量无限。QPS识别默认为10
- 2，最长支持60s的录音文件。对文件大小没有限制，只对时长有限制。
- 3.Android SDK：支持Android 2.3及以上系统，支持ARM\X86架构。安装包最小增加200k，支持8k/16k采样率，支持pcm格式。 iOS SDK：支持iOS 5.0及以上系统，支持ARM-v7\ARM-v7s\ARM64\i386\x86_64架构。安装包最小增加400k，支持8k/16k采样率，支持pcm格式。
- 4.目前语音基础服务全部免费。
- 5.语音识别支持：安卓+IOS支持4个语言：中文普通话、中文四川话、粤语、英语
## API4.加分项
使用复杂度：调用2个API
- 1.讯飞声纹识别API        
- 2.百度文本情绪识别    

