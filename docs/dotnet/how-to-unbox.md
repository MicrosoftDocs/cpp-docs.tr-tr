---
title: 'Nasıl yapılır: Açma'
ms.date: 11/04/2016
helpviewer_keywords:
- unboxing
ms.assetid: 75794696-9275-47bf-9a7d-5abe6585ab91
ms.openlocfilehash: b2919ecce254a81d6a140fc7906d28646b50ab8e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618536"
---
# <a name="how-to-unbox"></a>Nasıl yapılır: Açma

Açma ve bir değer değiştirme işlemi gösterilmektedir.

## <a name="example"></a>Örnek

```
// vcmcppv2_unboxing.cpp
// compile with: /clr
using namespace System;

int main() {
   int ^ i = gcnew int(13);
   int j;
   Console::WriteLine(*i);   // unboxing
   *i = 14;   // unboxing and assignment
   Console::WriteLine(*i);
   j = safe_cast<int>(i);   // unboxing and assignment
   Console::WriteLine(j);
}
```

```Output
13
14
14
```

## <a name="see-also"></a>Ayrıca Bkz.

[Kutulama](../windows/boxing-cpp-component-extensions.md)