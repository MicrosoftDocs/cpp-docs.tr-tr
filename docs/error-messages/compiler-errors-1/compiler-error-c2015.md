---
title: Derleyici hatası C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 5453009e1c2bd091ed3507f3c43bd7fcecd33abc
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743106"
---
# <a name="compiler-error-c2015"></a>Derleyici hatası C2015

Sabitte çok fazla karakter

Bir karakter sabiti ikiden fazla karakter içeriyor. Sınır, standart karakter sabitleri için bir karakter ve uzun karakter sabitleri için iki karakterdir.

\T gibi bir kaçış sırası, tek bir karaktere dönüştürülür.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2015 oluşturur:

```cpp
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

C2015, bir Microsoft uzantısı kullanılırken de gerçekleşebilir, karakter sabitleri tamsayılara dönüştürülür.  Aşağıdaki örnek C2015 oluşturur:

```cpp
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```
