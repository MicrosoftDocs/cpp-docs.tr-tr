---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3066'
title: Derleyici hatası C3066
ms.date: 03/28/2017
f1_keywords:
- C3066
helpviewer_keywords:
- C3066
ms.assetid: 226f6de5-c4c5-41e2-b31a-2e30a37fbbeb
ms.openlocfilehash: 68e348e14ddababe96123d31812e2f650e14b52f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281697"
---
# <a name="compiler-error-c3066"></a>Derleyici hatası C3066

Bu tür bir nesnenin bu bağımsız değişkenlerle çağrılması için birden çok yol vardır

Derleyici, yedekleri içeren belirsiz bir işlev çağrısı algıladı.

Aşağıdaki örnek C3066 oluşturur:

```cpp
// C3066.cpp
template <class T, class U> void func(T*, U*){}

typedef void (*PF)(const int*, const char*);
typedef void (*PF1)(const int*, volatile char*);

struct A {
   operator PF() const {
      return func;
   }

   operator PF1() {
      return func;
   }

   operator PF1() const  {
      return func;
   }

};

int main() {
   A a;
   int i;
   char c;

   a(&i, &c);   // C3066
   a(&i, (const char *) &c);   // OK
}
```

## <a name="copy-list-initialization"></a>Kopya listesini başlatma

Visual Studio 2015 ' de, derleyici yanlışlıkla kopyalama-liste başlatmasını düzenli kopya başlatma ile aynı şekilde kabul ediyor; yalnızca aşırı yükleme çözümlemesi için Oluşturucu dönüştürmekte sayılır. Aşağıdaki örnekte, Visual Studio 2015 myInt (23) öğesini seçer ancak Visual Studio 2017 hatayı doğru bir şekilde yükseltir.

```
// From http://www.open-std.org/jtc1/sc22/wg21/docs/cwg_closed.html#1228
struct MyList {
       explicit MyStore(int initialCapacity);
};

struct MyInt {
       MyInt(int i);
};

struct Printer {
       void operator()(MyStore const& s);
       void operator()(MyInt const& i);
};

void f() {
       Printer p;
       p({ 23 }); // C3066: there are multiple ways that an object of this type can be called with these arguments
}
```
