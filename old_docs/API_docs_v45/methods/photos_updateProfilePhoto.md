---
title: photos.updateProfilePhoto
description: photos.updateProfilePhoto parameters, return type and example
---
## Method: photos.updateProfilePhoto  
[Back to methods index](index.md)


### Parameters:

| Name     |    Type       | Required |
|----------|:-------------:|---------:|
|id|[InputPhoto](../types/InputPhoto.md) | Yes|
|crop|[InputPhotoCrop](../types/InputPhotoCrop.md) | Yes|


### Return type: [UserProfilePhoto](../types/UserProfilePhoto.md)

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

$UserProfilePhoto = $MadelineProto->photos->updateProfilePhoto(['id' => InputPhoto, 'crop' => InputPhotoCrop, ]);
```

Or, if you're using the [PWRTelegram HTTP API](https://pwrtelegram.xyz):

### As a bot:

POST/GET to `https://api.pwrtelegram.xyz/botTOKEN/madeline`

Parameters:

* method - photos.updateProfilePhoto
* params - `{"id": InputPhoto, "crop": InputPhotoCrop, }`



### As a user:

POST/GET to `https://api.pwrtelegram.xyz/userTOKEN/photos.updateProfilePhoto`

Parameters:

id - Json encoded InputPhoto
crop - Json encoded InputPhotoCrop



Or, if you're into Lua:

```
UserProfilePhoto = photos.updateProfilePhoto({id=InputPhoto, crop=InputPhotoCrop, })
```

