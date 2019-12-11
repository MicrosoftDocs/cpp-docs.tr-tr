---
title: Derleyici Uyarısı (düzey 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: c361563c2272da002a0edc185cc924c64f6b5e5c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991666"
---
# <a name="compiler-warning-level-3-c4995"></a>Derleyici Uyarısı (düzey 3) C4995

' function ': ad kullanım dışı #pragma olarak işaretlendi

Derleyici [pragma ile](../../preprocessor/deprecated-c-cpp.md)işaretlenmiş bir işlevle karşılaştı. İşlev, gelecekteki bir sürümde desteklenmiyor olabilir. Bu uyarıyı [Uyarı](../../preprocessor/warning.md) pragması (Aşağıdaki örnek) ile kapatabilirsiniz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4995 oluşturur:

```cpp
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```
