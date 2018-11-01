---
title: Derleyici Hatası C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 094a794627b886abc7db5ba4d74c6fe97ff82461
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50649750"
---
# <a name="compiler-error-c2086"></a>Derleyici Hatası C2086

'identifier': yeniden tanımlama

Tanımlayıcı, birden çok kez tanımlanmış veya önceki bir sonraki bildirimi farklıdır.

C2086 da başvurulan bir C# derleme için artımlı oluşturmayı sonucu olabilir. Bu hatayı çözmek için C# derleme yeniden oluşturun.

Aşağıdaki örnek, C2086 oluşturur:

```
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```