import requests
from bs4 import BeautifulSoup
import json
import re
import time
import random

headers = {"User-Agent" : "Mozilla/5.0 (Windows NT 6.1; WOW64; rv:34.0) Gecko/20100101 Firefox/34.0 "}
url = "http://www.wandoujia.com/category/5014/"
headers2 = [{"User-Agent":"Mozilla/5.0 (Macintosh; U; Intel Mac OS X 10_6_8; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50"},
            {"User-Agent":"Mozilla/5.0 (Windows; U; Windows NT 6.1; en-us) AppleWebKit/534.50 (KHTML, like Gecko) Version/5.1 Safari/534.50"},
            {"User-Agent":"Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; Trident/5.0;"},
            {"User-Agent":"Mozilla/5.0 (Macintosh; Intel Mac OS X 10.6; rv:2.0.1) Gecko/20100101 Firefox/4.0.1"},
            {"User-Agent":"Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Trident/4.0; SE 2.X MetaSr 1.0; SE 2.X MetaSr 1.0; .NET CLR 2.0.50727; SE 2.X MetaSr 1.0)"},
            {"User-Agent":"Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)"},
            {"User-Agent":"Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; The World)"},
            {"User-Agent":"Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1)"},
            {"User-Agent":"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/65.0.3325.181 Safari/537.36"},
            {"User-Agent":"Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; 360SE)"},
            {"User-Agent":"Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 5.1; Maxthon 2.0)"}]

url_mi_1 = "http://app.mi.com/categotyAllListApi?page="
url_mi_2 = "&categoryId="
url_mi_3 = "&pageSize=30"

if __name__ == "__main__":
    for id in range(1, 100):
        for page in range(0, 10000):
            try:
                url = url_mi_1 + str(page)+url_mi_2 + str(id) + url_mi_3
                print(url)
                int_header = (int)(random.randint(0, 10) + random.random())
                r = requests.get(url, headers=headers2[int_header])
                soup = BeautifulSoup(r.text, 'html.parser')

                # print(soup)
                pattern = re.compile("displayName\":\"(.*?)\",\"icon\"")
                finds = pattern.findall(str(soup))
                print(finds)
                if len(finds) != 0:
                    with open("app_mi1.2.txt", 'a', encoding='utf-8')as f:
                        for find_ in finds:
                            f.write(find_+'\n')

                print("----------page" + str(page) + " done!!----------")
            except:
                print("----------page" + str(page) + " fail!!----------")
                page -= 1
            if len(finds) == 0:
                break
