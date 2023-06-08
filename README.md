import requests
from bs4 import BeautifulSoup

# 发送HTTP请求并解析HTML
url = 'https://www.example.com'
response = requests.get(url)
soup = BeautifulSoup(response.text, 'html.parser')

# 提取页面内容
title = soup.title.string
links = [link.get('href') for link in soup.find_all('a')]

# 打印页面标题和链接
print('Title:', title)
print('Links:', links)
