---
title: Önemli hata C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: b6253af9fcf400321fb58d4d8a6d7aacf461b926
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577651"
---
# <a name="fatal-error-c1103"></a>Önemli hata C1103

önemli hata program kimliği içeri aktarılırken: 'message'

Derleyici, bir tür kitaplığı içeri aktarılırken bir sorun algıladı.  Örneğin, edemez bir tür kitaplığı ile program kimliği belirtin ve ayrıca belirtin `no_registry`.

Daha fazla bilgi için [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

Aşağıdaki örnek, C1103 oluşturur:

```
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```