---
title: Derleyici hatası C3287
description: Microsoft C++ derleyicisi hatası C3287 açıklanır.
ms.date: 09/25/2020
f1_keywords:
- C3287
helpviewer_keywords:
- C3287
ms.assetid: c1fa73d2-2c82-4136-a7da-0e75e3b420ad
ms.openlocfilehash: 4067355ef1bc1992d0f8519656bcd1063179aef4
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414327"
---
# <a name="compiler-error-c3287"></a>Derleyici hatası C3287

> '*Type*' türü (GetEnumerator 'ın dönüş türü) uygun bir ortak MoveNext üye işlevine ve genel Current özelliğine sahip olmalıdır

## <a name="remarks"></a>Açıklamalar

Kullanıcı tanımlı koleksiyon sınıfları ve için tanımlar içermelidir `MoveNext` `Current` .

Daha fazla bilgi için, [içindeki her bir için](../../dotnet/for-each-in.md)bkz..

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
