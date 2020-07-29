---
title: Derleyici Uyarısı (düzey 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: a192fb9d8dc046bb3493b90b85371175520ccf95
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230733"
---
# <a name="compiler-warning-level-1-c4258"></a>Derleyici Uyarısı (düzey 1) C4258

' Variable ': for döngüsünden gelen tanım yoksayıldı; kapsayan kapsamdaki tanım kullanılır "

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)altında, bir [for](../../cpp/for-statement-cpp.md) döngüsünde tanımlanmış değişkenler döngü bittikten sonra kapsam dışına çıkar **`for`** . Bu uyarı, döngü değişkeniyle aynı ada sahip olan ancak kapsayan döngüde tanımlanan bir değişken, döngüyü içeren kapsamda yeniden kullanıldığında oluşur **`for`** . Örnek:

```cpp
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
