---
title: Derleyici Hatası C3287
ms.date: 11/04/2016
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: ab0b93aa1a74ea79515e24ef2b1e289cf0227dac
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50538690"
---
# <a name="compiler-error-c3287"></a>Derleyici Hatası C3287

' % s'type 'türü' (GetEnumerator'ın dönüş türü) uygun ortak MoveNext üye işlevine ve genel Current özelliğine sahip olmalıdır

Kullanıcı tanımlı bir koleksiyon sınıfları, tanımlarını içermelidir `MoveNext` ve `Current`.

Bkz: [nasıl yapılır: her Iterate Over a User-Defined koleksiyonuyla](../../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md) daha fazla bilgi için.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3287 oluşturur.

```
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