# QA
## 1.原生dom与虚拟dom
因为dom操作是比较消耗性能的，所以有了虚拟dom。这样多次的dom操作就可以转移在多次的虚拟dom操作，然后有虚拟dom一次性反应在真实dom上，极大的提升性能