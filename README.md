# xfyun-node

![](https://camo.githubusercontent.com/ae91a5698ad80d3fe8e0eb5a4c6ee7170e088a7d/687474703a2f2f37786b6571692e636f6d312e7a302e676c622e636c6f7564646e2e636f6d2f61692f53637265656e25323053686f74253230323031372d30342d30342532306174253230382e32302e3437253230504d2e706e67)

# welcome
[科大讯飞](http://www.xfyun.cn/)没有提供Node.js SDK，于是就有了这个轮子。
* 目前仅支持 linux64，目前仅支持科大讯飞听写接口。

```
# download xfyun sdks from official portal, a zip file like here.
sudo unzip Linux_voice_1135_5864ae2d.zip -d /opt/xfy-sdk
cd PROJECT_ROOT
```

* Install
```
npm install xfy-node --save
```

## Usage
```
    const xfyclient = require('xfy-node');
    let params = {
        username: null, // 账号名称
        password: null, // 账号密码 
        appid: '5864ae2d', // AppID
        // 语言
        // zh_cn:简体中文
        // zh_tw:繁体中文
        // en_us:英语
        // 默认为zh_cn
        lang: 'zh_cn', 
        // 口音
        // mandarin:普通话
        // cantonese:粤语
        // 默认为mandarin
        accent: 'mandarin',
        // 音频格式
        // 8000, 16000, 默认为16000
        sample_rate: 16000,
        // 音频文件位置，绝对路径
        audio_file: 'wav/iflytek01.wav'
    }

    xfyclient.iat(params)
        .then(function (result) {
            console.log('result', result);
        }, function(err){
            console.log('err', err);
        });
```

## Tutorial
https://github.com/Samurais/xfy-node-getstarted

## Contribution
```
npm install
node-gyp rebuild
ava # test
```

## 讯飞提供的原始SDK
```
git clone https://github.com/Samurais/xfyun-get-started
```

## 资源链接
[语音识别科普](http://bbs.xfyun.cn/forum.php?mod=viewthread&tid=6911)

[服务介绍](http://www.xfyun.cn/doccenter/asr)

[开发者论坛](http://bbs.xfyun.cn/portal.php)

[识别英语](http://bbs.xfyun.cn/forum.php?mod=viewthread&tid=22602&extra=page%3D1)

# Copyright & License

Code & Docs 2017© Hai Liang Wang hailiang.hl.wang@gmail.com

Code released under the ISC license

Docs released under Creative Commons