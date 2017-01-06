### Formatting

* **Basicformatting**
```
  #old
  print(('%s %s') %('one','two'))
  #new
  print('{} {}'.format('one','two'))
```
```
  #old
  print(('%d %d') %(1,2))
  #new
  print('{} {}'.format(1,2))
```
```  
  #re-arranging the order
  print('{1} {0}'.format('one','two'))
```
```
  #escape braces
  print('My name is {0} - {{}}'.format('Yifan'))
```



