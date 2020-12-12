---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4232'
title: Derleyici Uyarısı (düzey 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: 272fdcbc856ef5e86a8ff043b5aeab98a36413a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291421"
---
# <a name="compiler-warning-level-4-c4232"></a>Derleyici Uyarısı (düzey 4) C4232

Standart olmayan uzantı kullanıldı: ' tanımlayıcı ': DllImport ' dllimport ' adresi statik değil; kimlik garanti edilmez

Microsoft uzantıları (/Ze) altında, statik olmayan bir değere değiştiriciyle belirtilen bir işlevin adresi olarak verebilirsiniz **`dllimport`** . ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bu hataya neden olur.

Aşağıdaki örnek C4232 oluşturur:

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
