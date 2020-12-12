---
description: 'Daha fazla bilgi edinin: nasıl yapılır: Işaretçileri ve dizileri sabitleme'
title: 'Nasıl yapılır: İşaretçiler ve Dizileri Sabitleme'
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- pointers, pinning
- arrays [C++], pinning
ms.assetid: ee783260-e676-46b8-a38e-11a06f1d57b0
ms.openlocfilehash: ab0e09e94c45cc31862ef8d0b6c0771bfeae115d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119141"
---
# <a name="how-to-pin-pointers-and-arrays"></a>Nasıl yapılır: İşaretçiler ve Dizileri Sabitleme

Yönetilen bir nesnede tanımlanan bir alt nesnenin sabitlenmesi, tüm nesnenin sabitlenmesini etkiler.  Örneğin, bir dizinin herhangi bir öğesi sabitse, tüm dizi da sabitlenmiş olur. Bir sabitlenmiş diziyi bildirmek için dile yönelik uzantı yok. Bir diziyi sabitlemek için, öğe türüne sabitleme işaretçisi bildirin ve öğelerinden birini sabitleyin.

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
