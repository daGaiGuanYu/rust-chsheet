# Generic
## �ſ�
##### ����
+ ����
+ �ṹ
+ ö��

##### ����ʱ���
+ ����ʱ
+ ʹ��ʱ

> ����ʱ������ʱ�ǶԼ�������ԣ�����ʱ��ʹ��ʱ�ǶԿ����߶���

##### ��Ϊ
�ڶ���ʱ��ָ��ĳЩ���ݵ����ͣ�����ʹ��ʱȷ����

##### Ŀ��
��Щ�����������������޹أ�����˵���ڲ�ͬ���������ͣ���Щ������һ���ģ�  
��ô�ڶ�����Щ����ʱ�����Բ�ָ��ĳһ�ֻ��������

## ʹ��
### Function
``` rust
fn ������<A, B, C, ...>(...) -> ... {

}
```

### Struct
``` rust
struct �ṹ��<A, B, C, ...> {

}
```

### Enum
``` rust
enum ö����<A, B, C, ...> {

}
```

### Method
##### ���ĳһ������ʵ��
��� `Point<f32>` ʵ��
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

##### ���������
``` rust
struct Point<T> {
  x: T,
  y: T
}

impl<T> Point<T> {
  // ...
}
```