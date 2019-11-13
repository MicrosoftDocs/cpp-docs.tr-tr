---
title: Derleyici Uyarısı (düzey 1) C4555
ms.date: 11/04/2016
f1_keywords:
- C4555
helpviewer_keywords:
- C4555
ms.assetid: 50b286c1-f7bf-4292-b1fa-baaac9538611
ms.openlocfilehash: e2c6a12b26754d7823252554950c124bdff4e6e8
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73965983"
---
# <a name="compiler-warning-level-1-c4555"></a>Derleyici Uyarısı (düzey 1) C4555

ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu

Bu uyarı, bir ifadenin hiçbir etkisi olmadığında size bildirir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

Örneğin:

```cpp
// C4555.cpp
// compile with: /W1
#pragma warning(default:4555)

void func1()
{
   1;   // C4555
}

void func2()
{
   int x;
   x;   // C4555
}

int main()
{
}
```