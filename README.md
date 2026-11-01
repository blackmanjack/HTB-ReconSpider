# HTB-ReconSpider
Web enumeration script provided by HackTheBox.

First, run this command in your terminal to download the custom scrapy spider, ReconSpider, and extract it to the current working directory.
```
blackmanjack@htb[/htb]$ wget -O ReconSpider.zip https://cdn.services-k8s.prod.aws.htb.systems/content/modules/144/ReconSpider.v1.2.zip
blackmanjack@htb[/htb]$ unzip ReconSpider.zip
```
With the files extracted, you can run ReconSpider.py using the following command:
```
blackmanjack@htb[/htb]$ python3 ReconSpider.py http://inlanefreight.com
```

Replace inlanefreight.com with the domain you want to spider. The spider will crawl the target and collect valuable information.

## results.json

After running ReconSpider.py, the data will be saved in a JSON file, results.json. This file can be explored using any text editor. Below is the structure of the JSON file produced:
```json
{
    "emails": [
        "lily.floid@inlanefreight.com",
        "cvs@inlanefreight.com",
        ...
    ],
    "links": [
        "https://www.themeansar.com",
        "https://www.inlanefreight.com/index.php/offices/",
        ...
    ],
    "external_files": [
        "https://www.inlanefreight.com/wp-content/uploads/2020/09/goals.pdf",
        ...
    ],
    "js_files": [
        "https://www.inlanefreight.com/wp-includes/js/jquery/jquery-migrate.min.js?ver=3.3.2",
        ...
    ],
    "form_fields": [],
    "images": [
        "https://www.inlanefreight.com/wp-content/uploads/2021/03/AboutUs_01-1024x810.png",
        ...
    ],
    "videos": [],
    "audio": [],
    "comments": [
        "<!-- #masthead -->",
        ...
    ]
}
```
Each key in the JSON file represents a different type of data extracted from the target website:

JSON Key	Description
```
emails	Lists email addresses found on the domain.
links	Lists URLs of links found within the domain.
external_files	Lists URLs of external files such as PDFs.
js_files	Lists URLs of JavaScript files used by the website.
form_fields	Lists form fields found on the domain (empty in this example).
images	Lists URLs of images found on the domain.
videos	Lists URLs of videos found on the domain (empty in this example).
audio	Lists URLs of audio files found on the domain (empty in this example).
comments	Lists HTML comments found in the source code.
```
By exploring this JSON structure, you can gain valuable insights into the web application's architecture, content, and potential points of interest for further investigation.
