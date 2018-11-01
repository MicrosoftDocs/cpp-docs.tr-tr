---
title: Derleyici Uyarısı (düzey 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a3ce4c81a86920baddfc1b277df0236a96254be4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50478284"
---
# <a name="compiler-warning-level-1-c4258"></a>Derleyici Uyarısı (düzey 1) C4258

'variable': tanımından döngü göz ardı edilir için; kapsayan kapsamdan gelen tanım kullanılan"

Altında [/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve [/ZC: forscope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md), tanımlanan değişkenler bir [için](../../cpp/for-statement-cpp.md) döngü Git kapsam dışına **için** döngü sona erer. İçeren kapsamı döngü değişkeni kapsayan bir döngü içinde tanımlanan ancak aynı ada sahip bir değişken tekrar kullanılıyorsa, bu uyarı oluşur **için** döngü. Örneğin:

```
// C4258.cpp
// compile with: /Zc:forScope /W1
int main()
{
   int i;
   {
      for (int i =0; i < 1; i++)
         ;
      i = 20;   // C4258 i (in for loop) has gone out of scope
   }
}
```