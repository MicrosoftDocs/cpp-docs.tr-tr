---
title: Derleyici Uyarısı (düzey 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: dee087b73bf032a68daf0527ea584efcc7579361
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50552639"
---
# <a name="compiler-warning-level-4-c4232"></a>Derleyici Uyarısı (düzey 4) C4232

Standart olmayan uzantı kullanıldı: 'identifier': 'dllimport' dllimport'un adresi statik değil; kimlik garanti edilemiyor

Microsoft Uzatmaları (/Ze) altında bir işlevin adresini ile bildirilen statik olmayan bir değer verebilirsiniz **dllimport** değiştiricisi. ANSI Uyumluluğu altında ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), bu bir hataya neden olur.

Aşağıdaki örnek, C4232 oluşturur:

```
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```