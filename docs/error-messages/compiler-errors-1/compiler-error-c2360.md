---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2360'
title: Derleyici hatası C2360
ms.date: 11/04/2016
f1_keywords:
- C2360
helpviewer_keywords:
- C2360
ms.assetid: 51bfd2ee-8108-4777-aa93-148b9cebfa83
ms.openlocfilehash: c71a82816edfacede51a5774fec5e90560d964a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136467"
---
# <a name="compiler-error-c2360"></a>Derleyici hatası C2360

' Identifier ' öğesinin başlatılması ' Case ' etiketiyle atlandı

Öğesinin başlatılması `identifier` bir **`switch`** bildirimde atlanabilir. Bildirim bir blok içine alınmadığı takdirde bir başlatıcıya sahip bir bildirimi atlayabilirsiniz. (Bir blok içinde bildirilmemiş değilse, değişken deyimin sonuna kadar kapsam içindedir **`switch`** .)

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
