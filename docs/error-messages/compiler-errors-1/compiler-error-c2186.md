---
title: Derleyici Hatası C2186
ms.date: 11/04/2016
f1_keywords:
- C2186
helpviewer_keywords:
- C2186
ms.assetid: 284bfb7e-ab85-4fcb-9864-1ddf7f6c94ae
ms.openlocfilehash: 191b7109640fd253b24d00d86021d909891a4f95
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523067"
---
# <a name="compiler-error-c2186"></a>Derleyici Hatası C2186

'operator': 'void' türünde geçersiz işlenen

İşlecin bir `void` işlenen.

Aşağıdaki örnek, C2186 oluşturur:

```
// C2186.cpp
// compile with: /c
void func1( void );
int  func2( void );
int i = 2 + func1();   // C2186 func1() is type void
int j = 2 + func2();   // OK both operands are type int
```