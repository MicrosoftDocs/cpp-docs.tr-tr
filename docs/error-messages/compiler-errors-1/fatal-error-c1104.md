---
title: Önemli hata C1104
ms.date: 11/04/2016
f1_keywords:
- C1104
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
ms.openlocfilehash: c10d1a89d854aaeac47a9a70f1e1e319d1662935
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174243"
---
# <a name="fatal-error-c1104"></a>Önemli hata C1104

Kitaplık kimliği içeri aktarılırken önemli hata: 'message'

Derleyici, bir tür kitaplığı içeri aktarılırken bir sorun algıladı.  Örneğin, edemez kitaplık kimliği ile bir tür kitaplığı belirtin ve ayrıca belirtin `no_registry`.

Daha fazla bilgi için [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

Aşağıdaki örnek, C1104 oluşturur:

```
// C1104.cpp
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104
```