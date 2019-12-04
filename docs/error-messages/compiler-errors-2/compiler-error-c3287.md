---
title: Derleyici hatası C3287
ms.date: 11/04/2016
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: f0f3441b749e3ae074e18e1132dcc4003eba3ba3
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749613"
---
# <a name="compiler-error-c3287"></a>Derleyici hatası C3287

' Type ' türü (GetEnumerator 'ın dönüş türü) uygun bir ortak MoveNext üye işlevine ve genel Current özelliğine sahip olmalıdır

Kullanıcı tanımlı koleksiyon sınıfları, `MoveNext` ve `Current`için tanımlar içermelidir.

Daha fazla bilgi için bkz. [nasıl yapılır: her biri Için Kullanıcı tanımlı bir koleksiyon üzerinden yineleme yapma](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C3287 oluşturur.

```cpp
// C3287.cpp
// compile with: /clr
using namespace System;

ref struct R {
   bool MoveNext() {
      return true;
   }
   property Object^ Current {
      Object^ get() {
         Object ^ o = gcnew Object;
         return o;
      }
   }
};

ref struct R2 {
   R ^GetEnumerator() {
      R^ r = gcnew R;
      return r;
   }
};

ref struct T {};

ref struct T2 {
   T ^GetEnumerator() {
      T^ t = gcnew T;
      return t;
   }
};

int main() {
   for each (int i in gcnew T2) {}   // C3287
   for each (int i in gcnew R2) {}   // OK
}
```
