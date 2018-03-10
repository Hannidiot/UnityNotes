# 判断点击事件是否点击在UI上

参考链接:http://www.xuanyusong.com/archives/3327

参考Unity Scripting API 关键字: EventSystem.isPointerOverGameObject();

```cs
using UnityEngine.EventSystem;

void Update() {
    if(Input.GetMouseDown(0))       // 如果点击左键
    {
        if(EventSystem.current.IsPointerOverGameObject())
            Debug.Log("触摸在UI上");
        else
            Debug.Log("没触摸在UI上");
    }
}
```
