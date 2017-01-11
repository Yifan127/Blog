### Chinese characters decoding

There are **Chinese characters** in weather_info.txt, so I get this exception:

    UnicodeDecodeError: 'gbk' codec can't decode byte 0xb4 in position 9: illegal multibyte sequence

**Thinking**:

1. The data in weather_info.txt is encoding in utf-8
2. Python needs to decode the unicode
3. But get the decode error: gbk can't decode
4. In Windows CMD, default encoding is gbk
5. So the question is : how to read unicode data from a file, and decode the data?

**Solution**: from [Python3 docs Unicode Howto](https://docs.python.org/3/howto/unicode.html)
```python
with open("weather_info.txt", encoding = "utf-8") as file:
for line in file.readlines():
line = line.strip()
data = line.split(',')
```
**Summary: Use open("filename", "encoding=xxx") when reading unicode data from a file.**

I stucked on this issue for couple hours, and read several blogs about characters encoding and decoding in Python2 and Python3, here is the best one I have ever read!
[Python character encoding and decoding](http://ajucs.com/2015/11/10/Python-character-encoding-explained.html)