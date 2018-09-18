---
title: Derleyici Uyarısı (Düzey 3) C4557 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4557
dev_langs:
- C++
helpviewer_keywords:
- C4557
ms.assetid: 7d9db716-03b2-4ee5-9b09-ba8aa5aa7e4c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 97423da084c005e427b21043e75ebe850623c63b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055318"
---
# <a name="compiler-warning-level-3-c4557"></a>Derleyici Uyarısı (Düzey 3) C4557

'__assume' 'effect' etkisini içeriyor

Geçirilen değeri bir [__assume](../../intrinsics/assume.md) Deyim2 değiştirildi.

Varsayılan olarak bu uyarıyı kapalıdır. Bkz: [derleyici uyarıları emin olan kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.

Aşağıdaki örnek, C4557 oluşturur:

```
// C4557.cpp
// compile with: /W3
#pragma warning(default : 4557)
int main()
{
   int i;
   __assume(i++);   // C4557
}
```