---
title: Kullanıcı Tanımlı Dönüşümler (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined conversions [C++]
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
ms.openlocfilehash: bb7a30382bc586f4d324d47ef6e6757fac83f5ae
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988382"
---
# <a name="user-defined-conversions-ccli"></a>Kullanıcı Tanımlı Dönüşümler (C++/CLI)

Bu bölümde, dönüşümdeki türlerden biri bir değer türünün veya başvuru türünün bir başvurusu veya örneği olduğunda, Kullanıcı tanımlı dönüştürmeler (UDC) açıklanmaktadır.

## <a name="implicit-and-explicit-conversions"></a>Örtük ve açık dönüştürmeler

Kullanıcı tanımlı dönüştürme örtük ya da açık olabilir.  Dönüştürme bilgi kaybına yol içermiyorsa, bir UDC örtük olması gerekir. Aksi halde açık bir UDC tanımlanmalıdır.

Yerel bir sınıfın Oluşturucusu, bir başvuruyu veya değer türünü yerel bir sınıfa dönüştürmek için kullanılabilir.

Dönüştürmeler hakkında daha fazla bilgi için bkz. [paketleme](../extensions/boxing-cpp-component-extensions.md) ve [Standart dönüşümler](../cpp/standard-conversions.md).

```cpp
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

Convert-from işleçleri, başka bir sınıfın bir nesnesinden tanımlandığı sınıfın bir nesnesini oluşturur.

Standart C++ , Convert-from işleçlerini desteklemez; Standart C++ bu amaçla oluşturucular kullanır. Ancak, CLR türleri kullanılırken, Visual C++ , Convert-from işleçlerini çağırmak için sözdizimsel destek sağlar.

Diğer CLS uyumlu dillerle birlikte çalışmak için, belirli bir sınıf için her kullanıcı tanımlı birli oluşturucuyu karşılık gelen bir Convert-from işleci ile kaydırmak isteyebilirsiniz.

Convert-from işleçleri:

- Statik işlev olarak tanımlanacak.

- Örtük olabilir (short-int gibi duyarlık kaybı olmayan dönüştürmeler için) ya da bir duyarlık kaybı olduğunda açık olabilir.

- , Kapsayan sınıfın bir nesnesini döndürür.

- Tek parametre türü olarak "Kimden" türüne sahip olacaktır.

Aşağıdaki örnekte örtük ve açık bir "Convert-from", Kullanıcı tanımlı dönüştürme (UDC) işleci gösterilmektedir.

```cpp
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

## <a name="convert-to-operators"></a>Dönüştür işleçleri

Convert-to işleçleri, bir sınıfın bir nesneyi başka bir nesne için tanımlandığı bir nesne dönüştürür. Aşağıdaki örnek örtük, dönüştürmeli, Kullanıcı tanımlı bir dönüştürme işlecini gösterir:

```cpp
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

Açık bir Kullanıcı tanımlı dönüştürme dönüşümü işleci, verileri bir şekilde kaybedebilecek dönüştürmeler için uygundur. Açık bir Convert-to işlecini çağırmak için, bir cast kullanılması gerekir.

```cpp
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

## <a name="to-convert-generic-classes"></a>Genel sınıfları dönüştürmek için

Genel bir sınıfı T 'e dönüştürebilirsiniz.

```cpp
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

Bir dönüştürme Oluşturucu bir tür alır ve bunu bir nesne oluşturmak için kullanır.  Bir dönüştürme Oluşturucusu yalnızca doğrudan başlatma ile çağrılır; yayınlar dönüştürme oluşturucularını çağırmaz. Varsayılan olarak, dönüştürme oluşturucuları CLR türleri için açıktır.

```cpp
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

Bu kod örneğinde, örtük bir statik dönüştürme işlevi, açık bir dönüştürme Oluşturucusu ile aynı şeyi yapar.

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

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)
