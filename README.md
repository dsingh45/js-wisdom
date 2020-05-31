# js-wisdom
These are some random details of JS for JS lovers by a JS lover.

### Object.freeze is shallow freeze
It is a shallow freeze. 
```javascript
let Obj = {first: {second: 'val'}};
Object.freeze(Obj);
Obj.first = 'changed-first'; //nothing changes as expected
Obj.first.second = 'changed-second'; //changes the value 'val' to 'changed-second'
console.log(Obj); // {first: {second: 'changed-second'}}
``` 
Obj.first is frozen but you can still mutate Obj.first.second (deep) property.

### Spread Operator is shallow copy for Objects
```javascript
let a=[{t:1},{t:2},{t:3}]; 
let b=[...a]; 
a[1].t=100; //(now b[1].t will also change to 100 automatically) 
console.log(b[1].t === 100) //true
```
For premitive values it is not applicable.
```javascript
let c=[1,2,3,4,5]; 
let d=[...c];  
c[2]=100; //(this will not change d[2])
console.log(d[2] === 3); //true
```
