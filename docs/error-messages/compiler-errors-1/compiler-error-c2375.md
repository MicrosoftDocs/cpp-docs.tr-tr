---
title: Derleyici Hatası C2375
ms.date: 11/04/2016
f1_keywords:
- C2375
helpviewer_keywords:
- C2375
ms.assetid: 193c5e8b-1b20-4928-8a02-8c1cddaf2a26
ms.openlocfilehash: 162f1b13ea76a92db6fbef08124a1e46bc4e18a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452110"
---
# <a name="compiler-error-c2375"></a>Derleyici Hatası C2375

'function': yeniden tanımlama; bağlantı farklı

İşlev zaten farklı bir bağlantı tanımlayıcısı ile bildirilir.

Aşağıdaki örnek, C2375 oluşturur:

```
// C2375.cpp
// compile with: /Za /c
extern void func( void );
static void func( void );   // C2375
static void func2( void );   // OK
```