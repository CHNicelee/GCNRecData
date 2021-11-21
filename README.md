# GCNRec

## Dataset Usage

1. use Numpy to load .npy file：
```
import numpy as np
project_info = np.load("projects_info.npy", allow_pickle=True).tolist()
dataset_S = np.load("dataset_S.npy", allow_pickle=True).tolist()
dataset_L = np.load("dataset_L.npy", allow_pickle=True).tolist()
```

2. project_info
project_info is a dict, key is the ID of the project,  value is another dict.
Example:
```
{
  "1000":
  {
  "name":"project_name"
   "readme":"content",
   "about":"content",
   "language":"java" 
  }
}
```
Infomation can be retrived by following code:
```
for k in project_info:
    readme = project_info[k]['readme']
```

3. dataset_S and dataset_L
dataset_S and dataset_L are dict as well, key is the ID of the user,value is the behavior of the user.
Example:
```
{
  "22":
  [('star',1000), ('fork',1002)]
}
```
Infomation can be retrived by following code:
```
for k in dataset_S:
    for item in dataset_S[k]:
        behavior_type = item[0]
        project_id = item[1]
```

