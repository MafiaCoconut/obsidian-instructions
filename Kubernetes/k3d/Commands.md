Install

```sh
k3s cluster create <name> --config <path>
```


Create worker node
```sh
k3d node create agent --role agent --cluster k3s-test
```