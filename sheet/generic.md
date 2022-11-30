# Generic
## 概况
##### 对象
+ 函数
+ 结构
+ 枚举

##### 两个时间点
+ 定义时
+ 使用时

> 编译时和运行时是对计算机而言，定义时和使用时是对开发者而言

##### 行为
在定义时不指定某些数据的类型（而在使用时确定）

##### 目的
有些操作，与数据类型无关（或者说对于不同的数据类型，有些操作是一样的）  
那么在定义这些操作时，可以不指定某一种或多种类型

## 使用
### Function
``` rust
fn 函数名<A, B, C, ...>(...) -> ... {

}
```

### Struct
``` rust
struct 结构名<A, B, C, ...> {

}
```

### Enum
``` rust
enum 枚举名<A, B, C, ...> {

}
```

### Method
##### 针对某一种类型实现
针对 `Point<f32>` 实现
``` rust
struct Point<T> {
  x: T,
  y: T
}

impl Point<f32> {
  fn distance_from_origin(&self) -> f32 {
    (self.x.powi(2) + self.y.powi(2)).sqrt()
  }
}
```

##### 不针对类型
``` rust
struct Point<T> {
  x: T,
  y: T
}

impl<T> Point<T> {
  // ...
}
```
