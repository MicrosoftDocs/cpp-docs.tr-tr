---
title: Derleyici hatası C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: eae1e7ddbc34d36b55d7afa424c137db00ef047d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757351"
---
# <a name="compiler-error-c3364"></a>Derleyici hatası C3364

' Delegate ': temsilci Oluşturucu: bağımsız değişken, yönetilen sınıfın veya genel işlevin üye işlevine işaretçi olmalıdır

Temsilcinin oluşturucusunun ikinci parametresi bir üye işlevin adresini ya da herhangi bir sınıfın statik üye işlevinin adresini alır. Her ikisi de basit adresler olarak değerlendirilir.

Aşağıdaki örnek C3364 oluşturur:

```cpp
// C3364_2.cpp
// compile with: /clr

delegate int D( int, int );

ref class C {
public:
   int mf( int, int ) {
      return 1;
   }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364

   // try the following line instead
   // System::Delegate^ pD = gcnew D(pC, &C::mf);
}
```
