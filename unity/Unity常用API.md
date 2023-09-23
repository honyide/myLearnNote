# Unity常用API

## 怪物朝主角的移动

1.直接使用Translate方法

```
transform.LookAt(player.transform.position);
transform.Translate(Vector3.forward*5*Time.deltaTime);
```

2.使用NavMeshAgent

```
using UnityEngime.AI
public class Solution{
private NavMeshAgent mNavAgent;
public void MoveTo(Vector3 targetPosition ){
mNavAgent.SetDestination(targetPosition);
}
}
```

3.角色状态机，finit状态机
