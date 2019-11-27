---
title: Derleyici Uyarısı (düzey 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: 4c31023fbcb36c53a7d0f5138c280ff12c4d495e
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541172"
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