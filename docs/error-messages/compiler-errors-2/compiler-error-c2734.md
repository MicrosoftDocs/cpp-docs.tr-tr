---
title: Derleyici Hatası C2734
ms.date: 11/04/2016
f1_keywords:
- C2734
helpviewer_keywords:
- C2734
ms.assetid: e53a77b7-825c-42d1-a655-90e1c93b833e
ms.openlocfilehash: c20fcc7673c00ea7cfad32bdc3feae042f1f9086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445363"
---
# <a name="compiler-error-c2734"></a>Derleyici Hatası C2734

'identifier': const nesnesi değil extern değilse başlatılmalıdır

Bildirilmiş bir tanımlayıcı `const` ancak başlatılmadı veya `extern`.

Aşağıdaki örnek, C2734 oluşturur:

```
// C2734.cpp
const int j;   // C2734
extern const int i;   // OK, declared as extern
```