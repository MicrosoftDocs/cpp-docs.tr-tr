---
title: Derleyici Hatası C3145
ms.date: 11/04/2016
f1_keywords:
- C3145
helpviewer_keywords:
- C3145
ms.assetid: f165c874-0f51-45c7-85e8-ebe321cbc168
ms.openlocfilehash: e425402bcea3e08764a9a89abfbd9316ca254a83
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598542"
---
# <a name="compiler-error-c3145"></a>Derleyici Hatası C3145

'object': WinRT türü 'type' ya da genel veya statik değişken yönetilmeyen

Yalnızca CLR veya WinRT nesneleri işlev kapsamı içinde tanımlayabilirsiniz.

Aşağıdaki örnek, C3145 oluşturur ve bu sorunun nasıl gösterir:

```
// C3145.cpp
// compile with: /clr
using namespace System;
ref class G {};

G ^ ptr;   // C3145
G ^ ptr2 = gcnew G;   // C3145

ref class GlobalObjects {
public:
   static G ^ ptr;   // OK
   static G ^ ptr2 = gcnew G;   // OK
};

int main() {
   G ^ ptr;   // OK
   G ^ ptr2 = gcnew G;   // OK
}
```

Aşağıdaki örnek, C3145 oluşturur:

```
// C3145b.cpp
// compile with: /clr
ref class MyClass {
public:
   static int data;
};

interior_ptr<int> p = &(MyClass::data);   // C3145

void Test(interior_ptr<int> x) {}

int main() {
   MyClass ^ h_MyClass = gcnew MyClass;
   interior_ptr<int> p = &(h_MyClass->data);
}
```
