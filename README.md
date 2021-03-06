
#   VKStatic class <img src="https://img.shields.io/badge/version-4-red.svg"> <img src="https://img.shields.io/badge/php-7-blue.svg"> <img src="https://img.shields.io/badge/update-10 Apr 2018-4a76a8.svg">
 
Simply script for scanning the wall VK

## Settings and start
``` php
require 'VKStatic.class.php';

try 
{
	// required parameters
	$data['access_token'] = 'token';
	
	// optinal parameters
	$data['owner_id'] = 19933;
	$data['filter'] = 'all';
	$data['v'] = '5.73';
	
	$vk = (new VKStatic($data))->wall_scan();

	echo $vk;
}
catch (\Exception $e)
{
	echo $e->getMessage();
	exit();
}

```
## Settings

* access_token - required parameter
* ownder_id - optional parameter, if not specify, the token id will be used
* filter - optional parameter, default - all (allowable values ALL or OWNER ])

## The result

The result will be given in json format. On the example of the statistics of the wall of Pavel Durov

```json
{
  "response": 
  {
    "likes": 20060612,
    "comments": 1790532,
    "reposts": 905430,
    "views": 94388476,
    "attachments": 
    {
      "count": 267,
      "type": 
      {
        "video": 4,
        "link": 29,
        "photo": 210,
        "doc": 10,
        "poll": 4,
        "photos_list": 1,
        "page": 4,
        "album": 1,
        "note": 3,
        "graffiti": 1
      }
    }
  }
}

```
## License

This library is licensed under the [MIT License](https://github.com/wnull/VKStatic/blob/master/LICENSE).
