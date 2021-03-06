---
title: account.sendChangePhoneCode
description: account.sendChangePhoneCode parameters, return type and example
---
## Method: account.sendChangePhoneCode  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|phone\_number|[string](../types/string.md) | Yes|


### Return type: [account\_SentChangePhoneCode](../types/account_SentChangePhoneCode.md)

### Example:


```
$MadelineProto = new \danog\MadelineProto\API();
if (isset($token)) { // Login as a bot
    $MadelineProto->bot_login($token);
}
if (isset($number)) { // Login as a user
    $sentCode = $MadelineProto->phone_login($number);
    echo 'Enter the code you received: ';
    $code = '';
    for ($x = 0; $x < $sentCode['type']['length']; $x++) {
        $code .= fgetc(STDIN);
    }
    $MadelineProto->complete_phone_login($code);
}

$account_SentChangePhoneCode = $MadelineProto->account->sendChangePhoneCode(['phone_number' => 'string', ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - account.sendChangePhoneCode
* params - `{"phone_number": "string", }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/account.sendChangePhoneCode`

Parameters:

phone_number - Json encoded string



Or, if you're into Lua:

```
account_SentChangePhoneCode = account.sendChangePhoneCode({phone_number='string', })
```

