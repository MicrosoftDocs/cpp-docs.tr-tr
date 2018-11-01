---
title: Derleyici Uyarısı (düzey 4) C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: 24872bb0b42de77dde358dc29f99826b41638628
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516069"
---
# <a name="compiler-warning-level-4-c4131"></a>Derleyici Uyarısı (düzey 4) C4131

'function': eski stil bildirimci kullanıyor

Belirtilen işlev bildirimi prototip biçiminde değil.

Eski stil işlev bildirimleri prototip biçimine dönüştürülmelidir.

Aşağıdaki örnek, eski stil işlev bildirimi gösterilmektedir:

```
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

Aşağıdaki örnek, bir prototip form gösterir:

```
void addrec( char *name, int id )
{ }
```