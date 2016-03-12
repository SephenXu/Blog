先看下HashMap类的两个方法

    Set<Map.Entry<K,V>>	entrySet()
          Returns a Set view of the mappings contained in this map.

    Set<K>	keySet()
          Returns a Set view of the keys contained in this map.

即分别返回HashMap的键值映射视图与键视图。
<!--more-->
对应遍历的实现分别为：


    Map map = new HashMap();
    Iterator iter = map.entrySet().iterator();
    while (iter.hasNext()) {
      Map.Entry entry = (Map.Entry) iter.next();
      Object key = entry.getKey();
      Object val = entry.getValue();
    }

---

    Map map = new HashMap();
    Iterator iter = map.keySet().iterator();
    while (iter.hasNext()) {
      Object key = iter.next();
      Object val = map.get(key);
    }

在键值都需要遍历时，entrySet()的效率是比较高的，因为keySet()在取值时又遍历了一遍。
