vkontakte-wall-posting
=================

Vkontakte Wall Posting

An example of VK API usage. The code looks like

```php
require_once('/path/to/Vkontakte.php');

$accessToken = 'your access token';
$publicID = 'your public ID here';
$vkAPI = new \Junta\Vkontakte(['access_token' => $accessToken]);

$attachments = [
    'images' => [
        # attaching image by url
        [
            'type' => 'image',
            'url' => 'image-link'
        ],
        # attaching image by full file path
        [
            'type' => 'image',
            'path' => '/full/path/to/image'
        ]
    ]
    # attaching link (there can be only one)
    'link' => 'link-url'
];

if ($vkAPI->postToPublic($publicID, "Hello world", $attachments, ['#вконтакте api', '#автопостинг', '#первые шаги'])) {

    echo "Yeah, success!\n";

} else {

    echo "Error publishing post\n";

}

```
