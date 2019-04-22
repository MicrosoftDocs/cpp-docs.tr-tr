---
title: 'Nasıl yapılır: PIN işaretçiler ve dizileri'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: ae8c1da79f41cf9209f2765ce5aa2f7ca3d34aea
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59025691"
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

## <a name="see-also"></a>Ayrıca bkz.

[pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)