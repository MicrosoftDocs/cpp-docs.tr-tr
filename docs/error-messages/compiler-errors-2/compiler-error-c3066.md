---
title: Derleyici Hatası C3066
ms.date: 03/28/2017
f1_keywords:
- C3066
helpviewer_keywords:
- C3066
ms.assetid: 226f6de5-c4c5-41e2-b31a-2e30a37fbbeb
ms.openlocfilehash: 126175b44bf0e6f4a58bc0e675cfd0cac1acc1ba
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62182619"
---
# <a name="compiler-error-c3066"></a>Derleyici Hatası C3066

Bu türde bir nesne çağrılabilen birden çok yolla bu bağımsız değişken

Derleyici, temsilciler içeren bir belirsiz işlev çağrısı algıladı.

Aşağıdaki örnek, C3066 oluşturur:

```
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

## <a name="copy-list-initialization"></a>Kopya listesi başlatması

Visual Studio 2015'te derleyici deneyebileceğinizi kopya listesi başlatması normal kopya başlatma aynı şekilde ele; yalnızca oluşturucu aşırı yükleme çözümlemesi için dönüştürme kabul. Aşağıdaki örnekte, Visual Studio 2015 MyInt(23) ancak Visual Studio 2017 hata başlatır doğru şekilde seçer.

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