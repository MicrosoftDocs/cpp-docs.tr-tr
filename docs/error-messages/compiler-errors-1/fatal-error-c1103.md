---
title: Önemli hata C1103 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1103
dev_langs:
- C++
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9e48d827c58ebf41ce3cf3862cbfbeaa494cf76
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055955"
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