---
title: Derleyici hatası C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: 417763e8c26918d3cd83702b283244d1c13d9d1f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74735755"
---
# <a name="compiler-error-c2086"></a>Derleyici hatası C2086

' tanımlayıcı ': yeniden tanımlama

Tanımlayıcı birden çok kez tanımlanmış veya sonraki bir bildirim öncekinden farklı.

C2086, başvurulan C# bir derleme için artımlı oluşturma sonucu da olabilir. Bu hatayı C# çözmek için derlemeyi yeniden derleyin.

Aşağıdaki örnek C2086 oluşturur:

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
