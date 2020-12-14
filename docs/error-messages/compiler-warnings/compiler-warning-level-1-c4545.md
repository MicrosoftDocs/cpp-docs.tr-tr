---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4545'
title: Derleyici Uyarısı (düzey 1) C4545
ms.date: 11/04/2016
f1_keywords:
- C4545
helpviewer_keywords:
- C4545
ms.assetid: 43f8f34f-ed46-4661-95c0-c588c577ff73
ms.openlocfilehash: 15a86a537d6fdde7d1bc9a70f5bbacda64b939df
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97310733"
---
# <a name="compiler-warning-level-1-c4545"></a>Derleyici Uyarısı (düzey 1) C4545

virgülden önceki ifade bir bağımsız değişken listesi olmayan bir işlev olarak değerleniyor

Derleyici hatalı biçimlendirilmiş bir virgül ifadesi algıladı.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md).

Aşağıdaki örnek C4545 oluşturur:

```cpp
// C4545.cpp
// compile with: /W1
#pragma warning (default : 4545)

void f() { }

int main()
{
   *(&f), 10;   // C4545
   // try the following line instead
   // (*(&f))(), 10;
}
```
