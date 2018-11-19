import requests
import json
url="http://acm.swust.edu.cn/api/user/submit/statistic.do?timeType=1&rows=10&page=1"
zyx=requests.get(url)
mht=json.loads(zyx.text)
for i in mht["data"]["pagingList"]:
    print(i["realName"] )
