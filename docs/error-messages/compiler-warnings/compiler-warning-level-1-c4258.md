---
title: Derleyici Uyarısı (düzey 1) C4258
ms.date: 11/04/2016
f1_keywords:
- C4258
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
ms.openlocfilehash: 75d706fafacc5c1524915d063a7fa392cea01b4c
ms.sourcegitcommit: 0cfc43f90a6cc8b97b24c42efcf5fb9c18762a42
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/05/2019
ms.locfileid: "73624873"
---
# <a name="compiler-warning-level-1-c4258"></a>Derleyici Uyarısı (düzey 1) C4258

' Variable ': for döngüsünden gelen tanım yoksayıldı; kapsayan kapsamdaki tanım kullanılır "

[/Ze](../../build/reference/za-ze-disable-language-extensions.md) ve [/Zc: forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)altında, [for döngüsünde tanımlanan](../../cpp/for-statement-cpp.md) değişkenler, **for** döngüsü bittikten sonra kapsam dışına çıkar. Bu uyarı, döngü değişkeniyle aynı ada sahip olan ancak kapsayan döngüde tanımlanan bir değişken **için for** döngüsünü içeren kapsamda yeniden kullanıldığında oluşur. Örneğin:

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