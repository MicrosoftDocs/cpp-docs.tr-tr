---
title: Kullanıcı Tanımlı Dönüşümler (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
ms.openlocfilehash: 047b2cc0ebc65d29f5f25d1bdf50b68da58c75d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553740"
---
# <a name="user-defined-conversions-ccli"></a>Kullanıcı Tanımlı Dönüşümler (C++/CLI)

Bu bölümde, türlerinden dönüştürme bir başvuru veya değer türü veya başvuru türü örneği olduğunda kullanıcı tanımlı Dönüşümler (UDC) açıklanmaktadır.

## <a name="implicit-and-explicit-conversions"></a>Örtük ve açık dönüştürmeler

Bir kullanıcı tanımlı dönüştürme örtük veya açık olarak ya da olabilir.  Bir UDC dönüşüm bilgi kaybına sağlamazsa örtülü olmalıdır. Aksi takdirde bir açık UDC tanımlanmalıdır.

Yerel bir sınıfın oluşturucusu, yerel bir sınıfa bir başvuru veya değer türü dönüştürmek için kullanılabilir.

Dönüştürmeler hakkında daha fazla bilgi için bkz. [kutulama](../windows/boxing-cpp-component-extensions.md) ve [standart dönüştürmeler](../cpp/standard-conversions.md).

```
// mcpp_User_Defined_Conversions.cpp
// compile with: /clr
#include "stdio.h"
ref class R;
class N;

value class V {
   static operator V(R^) {
      return V();
   }
};

ref class R {
public:
   static operator N(R^);
   static operator V(R^) {
      System::Console::WriteLine("in R::operator N");
      return V();
   }
};

class N {
public:
   N(R^) {
      printf("in N::N\n");
   }
};

R::operator N(R^) {
   System::Console::WriteLine("in R::operator N");
   return N(nullptr);
}

int main() {
   // Direct initialization:
   R ^r2;
   N n2(r2);   // direct initialization, calls constructor
   static_cast<N>(r2);   // also direct initialization

   R ^r3;
   // ambiguous V::operator V(R^) and R::operator V(R^)
   // static_cast<V>(r3);
}
```

**Output**

```Output
in N::N
in N::N
```

## <a name="convert-from-operators"></a>Dönüştürme Kaynağı İşleçleri

Dönüştürme kaynağı işleçleri işleci tanımlandığı sınıfın bir nesnesi, bir nesnenin başka bir sınıf oluşturun.

Standart C++ dönüştürme kaynağı işleçleri desteklemez; Standart C++ oluşturucular bu amaç için kullanır. Ancak, CLR Türleri kullanırken, Visual C++ söz dizimi desteğini sağlar dönüştürme kaynağı işleçleri çağırmak için.

De CLS uyumlu diğer dillerle birlikte çalışmak için belirli bir sınıfın her tekil kullanıcı tanımlı oluşturucusu bir karşılık gelen dönüştürme kaynağı işleci ile sarmalamak isteyebilirsiniz.

Dönüştürme kaynağı işleçleri:

- Statik işlevler olarak tanımlanmalıdır.

- Bir duyarlık kaybı olabilir, ya da (short int gibi duyarlık kaybı dönüştürme için) örtük veya açık, olabilir.

- İçerilen sınıfının bir nesnesi döndürür.

- Sahip olamaz "Kimden" türü tek bir parametre türü olarak.

Aşağıdaki örnek, bir örtük ve açık "convert-", kullanıcı tanımlı dönüştürmeden (UDC) işlecini gösterir.

```
// clr_udc_convert_from.cpp
// compile with: /clr
value struct MyDouble {
   double d;

   MyDouble(int i) {
      d = static_cast<double>(i);
      System::Console::WriteLine("in constructor");
   }

   // Wrap the constructor with a convert-from operator.
   // implicit UDC because conversion cannot lose precision
   static operator MyDouble (int i) {
      System::Console::WriteLine("in operator");
      // call the constructor
      MyDouble d(i);
      return d;
   }

   // an explicit user-defined conversion operator
   static explicit operator signed short int (MyDouble) {
      return 1;
   }
};

int main() {
   int i = 10;
   MyDouble md = i;
   System::Console::WriteLine(md.d);

   // using explicit user-defined conversion operator requires a cast
   unsigned short int j = static_cast<unsigned short int>(md);
   System::Console::WriteLine(j);
}
```

**Output**

```Output
in operator
in constructor
10
1
```

## <a name="convert-to-operators"></a>Dönüştürme için işleçleri

İşleci için başka bir nesne tanımlandığı sınıfın bir nesnesi için dönüştürme işleçleri dönüştürün. Aşağıdaki örnek, bir örtülü dönüştürme için kullanıcı tanımlı dönüştürme işleci gösterir:

```
// clr_udc_convert_to.cpp
// compile with: /clr
using namespace System;
value struct MyInt {
   Int32 i;

   // convert MyInt to String^
   static operator String^ ( MyInt val ) {
      return val.i.ToString();
   }

   MyInt(int _i) : i(_i) {}
};

int main() {
   MyInt mi(10);
   String ^s = mi;
   Console::WriteLine(s);
}
```

**Output**

```Output
10
```

Bir açık kullanıcı tanımlı dönüştürme dönüştürme operatörü olabilecek şekilde veri kaybı dönüştürmeler için uygundur. Açık convert-işlecini çağırmak için bir yayın kullanılmalıdır.

```
// clr_udc_convert_to_2.cpp
// compile with: /clr
value struct MyDouble {
   double d;
   // convert MyDouble to Int32
   static explicit operator System::Int32 ( MyDouble val ) {
      return (int)val.d;
   }
};

int main() {
   MyDouble d;
   d.d = 10.3;
   System::Console::WriteLine(d.d);
   int i = 0;
   i = static_cast<int>(d);
   System::Console::WriteLine(i);
}
```

**Output**

```Output
10.3
10
```

## <a name="to-convert-generic-classes"></a>Genel sınıflar dönüştürmek için

Genel sınıf T'ye Dönüştür

```
// clr_udc_generics.cpp
// compile with: /clr
generic<class T>
public value struct V {
   T mem;
   static operator T(V v) {
      return v.mem;
   }

   void f(T t) {
      mem = t;
   }
};

int main() {
   V<int> v;
   v.f(42);
   int i = v;
   i += v;
   System::Console::WriteLine(i == (42 * 2) );
}
```

**Output**

```Output
True
```

Dönüştürme bir oluşturucu, bir türü alır ve bir nesne oluşturmak için kullanır.  Bir dönüştürme Oluşturucu yalnızca doğrudan başlatma ile çağrılır; yayınları dönüştürme oluşturucuları çağırma kullanılamaz. Varsayılan olarak, dönüştürme oluşturucuları CLR türleri için açık.

```
// clr_udc_converting_constructors.cpp
// compile with: /clr
public ref struct R {
   int m;
   char c;

   R(int i) : m(i) { }
   R(char j) : c(j) { }
};

public value struct V {
   R^ ptr;
   int m;

   V(R^ r) : ptr(r) { }
   V(int i) : m(i) { }
};

int main() {
   R^ r = gcnew R(5);

   System::Console::WriteLine( V(5).m);
   System::Console::WriteLine( V(r).ptr);
}
```

**Output**

```Output
5
R
```

Bu kod örneğinde, bir örtük statik dönüştürme işlevi açık bir dönüştürme Oluşturucu olarak aynı şeyi yapar.

```
public value struct V {
   int m;
   V(int i) : m(i) {}
   static operator V(int i) {
      V v(i*100);
      return v;
   }
};

public ref struct R {
   int m;
   R(int i) : m(i) {}
   static operator R^(int i) {
      return gcnew R(i*100);
   }
};

int main() {
   V v(13);   // explicit
   R^ r = gcnew R(12);   // explicit

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);

   // explicit ctor can't be called here: not ambiguous
   v = 5;
   r = 20;

   System::Console::WriteLine(v.m);
   System::Console::WriteLine(r->m);
}
```

**Output**

```Output
13
12
500
2000
```

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıflar ve Yapılar](../windows/classes-and-structs-cpp-component-extensions.md)