---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2015'
title: Derleyici hatası C2015
ms.date: 11/04/2016
f1_keywords:
- C2015
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
ms.openlocfilehash: 0c27dbf8f7383ebd6424e9482fd1ce8cc0839a39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220961"
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
