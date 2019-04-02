---
title: 'Nasıl yapılır: PIN işaretçiler ve dizileri'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: 0b75b9c59c24f276142f6b8b5d662f86bb04d177
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58787878"
---
# <a name="how-to-pin-pointers-and-arrays"></a>Nasıl yapılır: PIN işaretçiler ve dizileri

Yönetilen bir nesnenin içinde tanımlanmış bir alt nesneyi sabitleme tüm nesnesi sabitleme etkisi vardır.  Bir dizideki her öğe sabitlenmiş değilse, örneğin, ardından tüm dizi ayrıca sabitlenir. Sabitlenmiş bir diziyi bildirmek için bir dil için hiçbir uzantı vardır. Bir dizi sabitlemek için öğe türü ve PIN öğelerinden biri bir sabitleme işaretçisine bildirin.

## <a name="example"></a>Örnek

### <a name="code"></a>Kod

```cpp
// pin_ptr_array.cpp
// compile with: /clr
#include <stdio.h>
using namespace System;

int main() {
   array<Byte>^ arr = gcnew array<Byte>(4);
   arr[0] = 'C';
   arr[1] = '+';
   arr[2] = '+';
   arr[3] = '\0';
   pin_ptr<Byte> p = &arr[1];   // entire array is now pinned
   unsigned char * cp = p;

   printf_s("%s\n", cp); // bytes pointed at by cp
                         // will not move during call
}
```

```Output
++
```

## <a name="see-also"></a>Ayrıca Bkz.

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)