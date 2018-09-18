---
title: Derleyici Hatası C2015 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2015
dev_langs:
- C++
helpviewer_keywords:
- C2015
ms.assetid: 8f40af0a-3a5a-4d6a-8ed7-125966e6bfed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fb9c3ba86224906f749088b96e5daae364d99e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076053"
---
# <a name="compiler-error-c2015"></a>Derleyici Hatası C2015

çok fazla karakter sabiti

Bir karakter sabiti, ikiden fazla karakter içeriyor. , Bir karakter standart karakter sabitlerinin ve iki karakter uzunluğunda karakter sabitlerinin sınırdır.

Örneğin, \t kaçış dizisi için tek bir karakter dönüştürülür.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2015 oluşturur:

```
// C2015.cpp
// compile with: /c

char test1 = 'error';   // C2015
char test2 = 'e';   // OK
```

## <a name="example"></a>Örnek

C2015, bir Microsoft uzantısı tam sayılara dönüştürülür karakter sabitleri kullanırken da meydana gelebilir.  Aşağıdaki örnek, C2015 oluşturur:

```
// C2015b.cpp
#include <stdio.h>

int main()
{
    int a = 'abcde';   // C2015

    int b = 'a';   // 'a' = ascii 0x61
    printf_s("%x\n", b);
}
```