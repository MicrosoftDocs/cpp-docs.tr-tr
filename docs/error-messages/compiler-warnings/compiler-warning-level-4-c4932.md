---
title: Derleyici Uyarısı (düzey 4) C4932
ms.date: 11/04/2016
f1_keywords:
- C4932
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
ms.openlocfilehash: afeb27562c995bea38e9858c7ba3b279a98655cf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50515030"
---
# <a name="compiler-warning-level-4-c4932"></a>Derleyici Uyarısı (düzey 4) C4932

__identifier(identifier) ve \__identifier(identifier) ayırt

Derleyici ayırt silemiyor **_finally** ve `__finally` veya `__try` ve **_try** geçirilen bir parametre olarak [__tanımlayıcı](../../windows/identifier-cpp-cli.md). Neden şekilde, her ikisinin de aynı programda, tanımlayıcı olarak kullanılacak çalışmamalısınız bir [C2374](../../error-messages/compiler-errors-1/compiler-error-c2374.md) hata.

Aşağıdaki örnek, C4932 oluşturur:

```
// C4932.cpp
// compile with: /clr /W4 /WX
int main() {
   int __identifier(_finally) = 245;   // C4932
   int __identifier(__finally) = 25;   // C4932
}
```