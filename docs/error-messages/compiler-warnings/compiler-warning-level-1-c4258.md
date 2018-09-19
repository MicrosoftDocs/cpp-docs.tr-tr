---
title: Derleyici Uyarısı (düzey 1) C4258 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4258
dev_langs:
- C++
helpviewer_keywords:
- C4258
ms.assetid: bbb75e6d-6693-4e62-8ed3-b006a0ec55e3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4d9aacd6e3681a1eb42073df8a13d7ce72c5634
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46083541"
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