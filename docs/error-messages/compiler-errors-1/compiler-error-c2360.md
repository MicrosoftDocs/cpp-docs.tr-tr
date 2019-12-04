---
title: Derleyici hatası C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: 226fcd8a27c9abdb789b8191a5cf4e59cc4a66cc
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759912"
---
# <a name="compiler-error-c2360"></a>Derleyici hatası C2360

' Identifier ' öğesinin başlatılması ' Case ' etiketiyle atlandı

`identifier` başlatılması `switch` bildiriminde atlanabilir. Bildirim bir blok içine alınmadığı takdirde bir başlatıcıya sahip bir bildirimi atlayabilirsiniz. (Bir blok içinde bildirilmemiş değilse, değişken `switch` deyimin sonuna kadar kapsam içindedir.)

Aşağıdaki örnek C2360 oluşturur:

```cpp
// C2360.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      int i = 1;
      { int j = 1; }
   case 1 :   // C2360
      int k = 1;
   }
}
```

Olası çözüm:

```cpp
// C2360b.cpp
int main() {
   int x = 0;
   switch ( x ) {
   case 0 :
      { int j = 1; int i = 1;}
   case 1 :
      int k = 1;
   }
}
```
