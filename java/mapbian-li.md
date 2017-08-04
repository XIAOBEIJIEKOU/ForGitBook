#### 第一种:

#### ```Map map = new HashMap();``

#### ```Iterator iter = map.entrySet().iterator();``

#### ```while (iter.hasNext()) {``

#### ```    Map.Entry entry = (Map.Entry) iter.next();``

#### ```    Object key = entry.getKey();``

#### ```    Object val = entry.getValue();``

#### ```}``

#### 效率高,以后一定要使用此种方式！

> #### Tip：entryset只是遍历了第一次，他把key和value都放到了entry中，所以就快了

#### 第二种:

#### ```Map map = new HashMap();``

#### ```Iterator iter = map.keySet().iterator();``

#### ```while (iter.hasNext()) {``

#### ```    Object key = iter.next();``

#### ```    Object val = map.get(key);``

#### ```}``

#### 效率低,以后尽量少使用

> #### Tip：keySet其实是遍历了2次，一次是转为iterator，一次是从hashmap中取出key所对于的value



