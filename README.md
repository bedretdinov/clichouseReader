# clichouseReader
```python
import requests
import urllib
import io


class ClichouseReader:
     
        host = "http://xxxxxxxx:8123"
        params = {
            'user':'admin',
            'password':'xxxxxxxxxxxx', 
        } 
        
        @classmethod
        def get_pandas(cls, sql): 
            cls.params['query'] = sql 
            req = requests.get(cls.host,params=cls.params) 
            return pd.read_csv(io.BytesIO(req.content), sep='\t')
            
```
