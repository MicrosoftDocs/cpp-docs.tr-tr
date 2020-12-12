---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4548'
title: Derleyici Uyarısı (düzey 1) C4548
ms.date: 11/04/2016
f1_keywords:
- C4548
helpviewer_keywords:
- C4548
ms.assetid: 2cee817e-e463-4d90-bbd2-de120d48c101
ms.openlocfilehash: 7c0f88f6516b1069fa9ef13e56c5ca043f627820
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266006"
---
# <a name="compiler-warning-level-1-c4548"></a>Derleyici Uyarısı (düzey 1) C4548

virgülden önceki ifadenin etkisi yok; yan etkisi olan ifade bekleniyordu

Derleyici hatalı biçimlendirilmiş bir virgül ifadesi algıladı.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek C4548 oluşturur:

```cpp
// C4548.cpp
// compile with: /W1
#pragma warning (default : 4548)
int main()
{
   int i = 0, k = 0;

   if ( i, k )   // C4548
   // try the following line instead
   // if ( i = 0, k )
      i++;
}
```
