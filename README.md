# js-wisdom
These are random fun findings in JS for JS lovers by a JS lover.
### Object.freeze is shallow freeze
It is a shallow freeze. You can still mutate Obj.first.second (deep) property.
### Spread Operator is shallow copy for Objects
let a=[{t:1},{t:2},{t:3}]; b=[...a]; a[1].t=100; (now b[1].t will also change to 100 automatically)
But for premitive values it is not a problem.
let c=[1,2,3,4,5]; d=[...a]; c[2]=100; (this will not change d[2])
So for Objects it is a shallow copy and the objects keep the reference from before being spread.
