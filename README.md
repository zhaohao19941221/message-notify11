
## 消息通知组件
hyperf异常监控报警通知(钉钉群机器人、飞书群机器人、邮件、QQ 频道机器人、企业微信群机器人)支持hyperf3.1+

## 功能

* 监控发送应用异常
* 支持多种通道(钉钉群机器人、飞书群机器人、邮件、QQ 频道机器人、企业微信群机器人)
* 支持扩展自定义通道

## 环境要求

* hyperf >= 3.1

## 安装

```bash
composer require coderzhao/message-notify -vvv
```

## 配置文件

发布配置文件`config/message.php`

```bash
hyperf vendor:publish coderzhao/message-notify
```


## 使用
```php
Notify::make()->setChannel(DingTalkChannel::class)
->setTemplate(Text::class)
->setTitle('标题')->setText('内容')->setAt(['all'])->setPipeline('info')
->send();
```

## 通道

| 通道名称  | 命名空间                                   | 支持格式          |
|-------|----------------------------------------|---------------|
| 钉钉群   | \MessageNotify\Channel\DingTalkChannel | Text、Markdown |
| 飞书群   | \MessageNotify\Channel\FeiShuChannel   | Text、Markdown |
| 企业微信群 | \MessageNotify\Channel\WechatChannel   | Text、Markdown |

## 格式

| 格式名称     | 命名空间                             |
|----------|----------------------------------|
| Text     | \MessageNotify\Template\Text     |
| Markdown | \MessageNotify\Template\Markdown |

## 协议

MIT 许可证（MIT）。有关更多信息，请参见[协议文件](LICENSE)。

## 参考内容
完全照搬对应下面的项目,只是为了解决一些在3.1+以上版本的bug,做了小小的修改和完善
[VinchanGit/message-notify](https://github.com/VinchanGit/message-notify)
