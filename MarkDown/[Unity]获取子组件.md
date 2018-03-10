# 如何获取一个父组件中的子组件以及孙组件

参考链接：http://blog.csdn.net/u011185231/article/details/49591383

----

### 常规流程

**Method One**

```cs
using System.Collections;
using UnityEngine;

public class FindObject : MonoBehavior {
    // public 一个变量来接收拖拽赋值
    public Transform[] grandFa;

    // Use this for initilization
    void Start() {
        grandFa = GetComponentInChildren<Transfrom>();
        foreach(Transform child in grandFa) {
            print(child.name);
        }
    }
}
```

会打印出 grandFa 中的所有子孙组件

<br/>

**Method Two**
```cs
    public static Transform[] pos;

    void Start() {
        pos = new Transform[transform.childCount];
        for(int i=0; i < pos.Length; i++) {
            pos[i] = transform.GetChild(i);
        }
    }
```
pos[i] 表示脚本所挂在组件下的第 i 个子组件

*P.S. 尚未验证孙组件顺序*

----

### 如果某个物体未被激活会怎样
A: 未被激活的组件中所有组件不会被显示

<br/>

---

### 如何获取未被激活的组件
A:
```cs
    grandFa = GetComponentInChildren<Transform>(true);
```
