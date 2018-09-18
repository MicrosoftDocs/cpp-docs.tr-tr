---
title: Derleyici Uyarısı (düzey 4) C4932 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4932
dev_langs:
- C++
helpviewer_keywords:
- C4932
ms.assetid: 0b8d88cc-21f6-45cb-a9f5-1795b7db0dfa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1c9143406fc4b52d50b5dc68215fa796f5100fb7
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053927"
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