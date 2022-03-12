# optional的使用心得
## 1. 解决的问题
以更加优雅的代码实现对npe的判断，本质上来说，和我们自己使用if else 来判断
是否为npe是同样的效果，只不过利用if else,会导致代码显得有点臃肿。
## 2. 两种实现方式的对比
- 原始方式
```java
public String get(Person person) {
        if (person != null) {
            if (person.getA() != null) {
                if (person.getA().getB() != null) {
                    return person.getA().getB();
                }
            }
        }

        return "none";
    }
```
- optional 方式实现
```java
Person person = new Person();
        Optional.ofNullable(person)
                .map(p -> p.getA())
                .map(p -> p.getB())
                .orElse("none")
```
- 总结
从以上两种方式可以看出，optional实现方式更加优雅。
  
## 3. optional相关的功能
只要了解了optional可以解决的问题类型，相关的使用
看一下源码即可。



