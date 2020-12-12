---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2086'
title: Derleyici hatası C2086
ms.date: 11/04/2016
f1_keywords:
- C2086
helpviewer_keywords:
- C2086
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
ms.openlocfilehash: b98b4ed3896b11d8df434935c1b539f76640f24c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252083"
---
# <a name="compiler-error-c2086"></a>Derleyici hatası C2086

' tanımlayıcı ': yeniden tanımlama

Tanımlayıcı birden çok kez tanımlanmış veya sonraki bir bildirim öncekinden farklı.

C2086, başvurulan bir C# derlemesi için artımlı oluşturma sonucu da olabilir. Bu hatayı çözmek için C# derlemesini yeniden derleyin.

Aşağıdaki örnek C2086 oluşturur:

```cpp
// C2086.cpp
main() {
  int a;
  int a;   // C2086 not an error in ANSI C
}
```
