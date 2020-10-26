## Capmonster.cloud for Python ![GitHub release (latest by date)](https://img.shields.io/github/v/release/alperensert/python_capmonster) ![PyPI - Python Version](https://img.shields.io/pypi/pyversions/capmonster_python) ![GitHub watchers](https://img.shields.io/github/watchers/alperensert/python_capmonster?style=social) ![GitHub Repo stars](https://img.shields.io/github/stars/alperensert/python_capmonster?style=social)
Unofficial Capmonster.cloud library for Python3. \
Currently supporting ***ImageToText, NoCaptcha (Recaptcha v2) proxyless and proxy-on, Recaptchav3Proxyless***.
>At least 2x cheaper, up to 30x faster than manual recognition services.

```
pip install capmonster-python
```

### Examples
##### *ImageToTextTask*
```python
from python_capmonster import ImageToTextTask

capmonster = ImageToTextTask(client_key="YOUR CLIENT KEY")
taskId = capmonster.createTask(file_path="captcha.png")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *NoCaptchaTaskProxyless*
```python
from python_capmonster import NoCaptchaTaskProxyless

capmonster = NoCaptchaTaskProxyless(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *NoCaptchaTask*
```python
from python_capmonster import NoCaptchaTask

capmonster = NoCaptchaTask(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL", proxyAddress="8.8.8.8", proxyPort=8080, proxyLogin="login", proxyPassword="password", proxyType="http or https")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *RecaptchaV3TaskProxyless*
> default minimum score: 0.3 and default page_action: verify
```python
from python_capmonster import RecaptchaV3TaskProxyless

capmonster = RecaptchaV3TaskProxyless(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL", minimum_score=0.7, page_action="verify")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```

> For detailed documentation (not this library's) is here: [capmonster.cloud documentation](https://zennolab.atlassian.net/wiki/spaces/APIS/pages/491575/English+Documentation)

###### Things to add:
- FunCaptchaTask & FunCaptchaTaskProxyless.
- Directly send base64 encoded image to ImageToTextTask.
- Cookie support for NoCaptchaTask proxy-on and proxyless.