# Bulk_SMS_API
## Status Response 
    # 100 => Success
    # 101 => Insufficient Credit
    # 102 => Invalid User

## Sender ID Maximum Characters: 11
## SMS Length is 160 Characters but supports multiple

## 1.1 HTTP API

Endpoint
```lua
http://www.cloudservicezm.com/smsservice/httpapi
```

## Request Format
```lua
http://www.cloudservicezm.com/smsservice/httpapi?username=XXXXXXXX&password=XXXXXXX&
msg=Succesfully+delivering+SMS+&shortcode=2343&sender_id=XXXXXXXXX&phone=2609796693
50&api_key=121231313213123123
```

## 1.2 JSON API

Endpoint
```lua
http://www.cloudservicezm.com/smsservice/jsonapi
```

## REQUEST FORMAT

```json
"auth":{"username":"test","password":"testpasswd","sender_id":"TEST",,"short_code":"2345"},"
messages":[{"phone":"0975020473","message":"test1"},{"phone":"0975020473","message":"test
2"},{"phone":"0975020473","message":"test3"},{"phone":"0975020473","message":"test3"}]}
```

## 1.3 SMPP API

Endpoint
```lua
http://www.cloudservicezm.com
```

Username: xxxxxxx
Password : xxxxxx
Port : 2770
IP Address/URL: 192.64.116.31

## Note: Conforms to SMPP Version 3.4 Specifications


# EXAMPLES
## JSON PHP
```json
$url = 'http://www.cloudservicezm.com/smsservice/jsonapi'; 
//Initiate cURL.
$ch = curl_init($url); 
//The JSON data.
$jsonData=array();
$jsonData['auth']=array(
"username"=>"XXXXXX",
"password"=>"XXXXXXXX",
"sender_id"=>"XXXXXXXXX"
);
$jsonData['messages'] = array(
array(
'phone' => '0979669350',
'message' => 'test1'
 ),
 array(
'phone' => '260979669350',
'message' => 'test2'
 ),
 array(
'phone' => '955935402',
'message' => 'test3'
 ),
 array(
'phone' => '0979669350',
'message' => 'test4'
 )
);
$jsonDataEncoded = json_encode($jsonData);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $jsonDataEncoded);
curl_setopt($ch, CURLOPT_RETURNTRANSFER,1); 
curl_setopt($ch, CURLOPT_HTTPHEADER, array('Content-Type: application/json')); 
curl_setopt($ch,CURLOPT_RETURNTRANSFER, 0);
$result = curl_exec($ch);
?>
```

## HTTP API
```lua
<?php
$url="http://www.cloudservicezm.com/smsservice/httpapi?username=tes&password=test&msg=t
est+test&shortcode=2343&sender_id=XXXXXXXXX&phone=0979669350&api_key=121231313213
123123”;
$ch = curl_init(); 
curl_setopt($ch,CURLOPT_URL,$url);
curl_setopt($ch, CURLOPT_POST,1);
curl_setopt($ch, CURLOPT_RETURNTRANSFER,1); 
$result = curl_exec($ch);
?>
```