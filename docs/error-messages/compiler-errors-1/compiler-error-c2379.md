---
title: Derleyici Hatası C2379
ms.date: 11/04/2016
f1_keywords:
- C2379
helpviewer_keywords:
- C2379
ms.assetid: 37dc3015-a4af-4341-bbf3-da6150df7e51
ms.openlocfilehash: 1b3256efb6c0ff8236ba80a9ac681780f34fa8dd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643852"
---
# <a name="compiler-error-c2379"></a>Derleyici Hatası C2379

biçimsel parametre numarası yükseltildiğinde farklı türe sahip

Belirtilen parametre türü aracılığıyla varsayılan promosyonlar, bir önceki bildirimde türüyle uyumlu değil. Bu bir hatadır, ANSI C ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ve Microsoft uzantılı bir uyarı (**/Ze**).

Aşağıdaki örnek, C2379 oluşturur:

```
// C2379.c
// compile with: /Za
void func();
void func(char);   // C2379, char promotes to int
```