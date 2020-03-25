---
title: Derleyici Uyarısı (düzey 4) C4232
ms.date: 11/04/2016
f1_keywords:
- C4232
helpviewer_keywords:
- C4232
ms.assetid: f92028a5-4ddd-43c1-97f5-4f724e5e14af
ms.openlocfilehash: c0e79dfa4564960a5660f0932b142b436370ac05
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80173926"
---
# <a name="compiler-warning-level-4-c4232"></a>Derleyici Uyarısı (düzey 4) C4232

Standart olmayan uzantı kullanıldı: ' tanımlayıcı ': DllImport ' dllimport ' adresi statik değil; kimlik garanti edilmez

Microsoft uzantıları (/Ze) altında, statik olmayan bir değeri **dllimport** değiştiricisi ile belirtilen bir işlevin adresi olarak verebilirsiniz. ANSI uyumluluğu ([/za](../../build/reference/za-ze-disable-language-extensions.md)) altında bu hataya neden olur.

Aşağıdaki örnek C4232 oluşturur:

```c
// C4232.c
// compile with: /W4 /Ze /c
int __declspec(dllimport) f();
int (*pfunc)() = &f;   // C4232
```
