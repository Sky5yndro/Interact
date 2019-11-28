# Interact bot

#### API Wrapper
### API Wrapper
#### Send message
``` php
$bot = new \TelegramBot\Api\BotApi('YOUR_BOT_API_TOKEN');
$bot->sendMessage($chatId, $messageText);
```

#### Send document
```php
$bot = new \TelegramBot\Api\BotApi('YOUR_BOT_API_TOKEN');
$document = new \CURLFile('document.txt');
$bot->sendDocument($chatId, $document);
```

#### Send message with reply keyboard
```php
$bot = new \TelegramBot\Api\BotApi('YOUR_BOT_API_TOKEN');
$keyboard = new \TelegramBot\Api\Types\ReplyKeyboardMarkup(array(array("one", "two", "three")), true); // true for one-time keyboard
$bot->sendMessage($chatId, $messageText, null, false, null, $keyboard);
```

#### Send message with inline keyboard
```php
$bot = new \TelegramBot\Api\BotApi('YOUR_BOT_API_TOKEN');
@@ -65,6 +66,17 @@ $keyboard = new \TelegramBot\Api\Types\Inline\InlineKeyboardMarkup(
        
$bot->sendMessage($chatId, $messageText, null, false, null, $keyboard);
```
#### Send media group
```php
$bot = new \TelegramBot\Api\BotApi('YOUR_BOT_API_TOKEN');
$media = new \TelegramBot\Api\Types\InputMedia\ArrayOfInputMedia();
$media->addItem(new TelegramBot\Api\Types\InputMedia\InputMediaPhoto('https://avatars3.githubusercontent.com/u/9335727'));
$media->addItem(new TelegramBot\Api\Types\InputMedia\InputMediaPhoto('https://avatars3.githubusercontent.com/u/9335727'));
// Same for video
// $media->addItem(new TelegramBot\Api\Types\InputMedia\InputMediaVideo('http://clips.vorwaerts-gmbh.de/VfE_html5.mp4'));
$bot->sendMediaGroup($chatId, $media);
```

#### Client

@@ -88,7 +100,7 @@ try {
}
```

### Botan SDK
### Botan SDK (not supported more)

[Botan](http://botan.io) is a telegram bot analytics system based on [Yandex.Appmetrica](http://appmetrica.yandex.com/).
In this document you can find how to setup Yandex.Appmetrica account, as well as examples of Botan SDK usage.
