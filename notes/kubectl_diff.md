---
Date: 2021-08-24
Title: kubectl apply / diff をxargsを使って高速で終わらせる
Tags: Kubernetes Tips Shell
---

[link](https://blog.framinal.life/entry/2021/08/24/235859)

```sh
kubectl diff -f .
↓

ls . |  xargs -t -P$(ls | wc -l) -I {} kubectl diff -f {}

or

ls . |  xargs -t -P$(ls | wc -l) -I {} sh -c 'kubectl diff -f {} | tee -a /tmp/diff/{}.diff'
kubectl apply -f .

↓

ls . |  xargs -t -P$(ls | wc -l) -I {} kubectl apply --validate=true --dry-run=server -f {}
```
