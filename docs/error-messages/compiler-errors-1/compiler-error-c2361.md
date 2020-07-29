---
title: Derleyici hatası C2361
ms.date: 11/04/2016
f1_keywords:
- C2361
helpviewer_keywords:
- C2361
ms.assetid: efbdaeb9-891c-4f7d-97da-89088a8413f3
ms.openlocfilehash: b95c6459c0ff093d22f3e754f2c7fd6564d2b296
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221204"
---
# <a name="compiler-error-c2361"></a>Derleyici hatası C2361

' Identifier ' öğesinin başlatılması ' default ' etiketiyle atlandı

Öğesinin başlatılması `identifier` bir **`switch`** bildirimde atlanabilir. Bildirim bir blok içine alınmadığı takdirde bir başlatıcıya sahip bir bildirimi atlayabilirsiniz. (Bir blok içinde bildirilmemiş değilse, değişken deyimin sonuna kadar kapsam içindedir **`switch`** .)

Aşağıdaki örnek C2361 oluşturur:

```cpp
// C2361.cpp
void func( void ) {
   int x;
   switch (x) {
   case 0 :
      int i = 1;
      { int j = 1; }
   default :   // C2361 error
      int k = 1;
   }
}
```

Olası çözüm:

```cpp
// C2361b.cpp
// compile with: /c
void func( void ) {
   int x = 0;
   switch (x) {
   case 0 :
      { int j = 1; int i = 1;}
   default :
      int k = 1;
   }
}
```
