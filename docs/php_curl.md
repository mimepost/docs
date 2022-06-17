#This is a simple php curl example


```
<?php

$url = "https://api.mimepost.com/v1/";
$ch = curl_init();   
curl_setopt($ch, CURLOPT_RETURNTRANSFER, 1);   
curl_setopt($ch, CURLOPT_URL, $url);   
$res = curl_exec($ch);
if(curl_error($ch)) {
    echo "curl error occurred!. Error:" . curl_error($ch);
    exit;
}
echo $res;   


```


