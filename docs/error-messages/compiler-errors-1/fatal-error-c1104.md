---
description: 'Daha fazla bilgi edinin: önemli hata C1104'
title: Önemli hata C1104
ms.date: 11/04/2016
f1_keywords:
- C1104
helpviewer_keywords:
- C1104
ms.assetid: 45bd85c4-77d3-4d3c-b167-49c563aefb4d
ms.openlocfilehash: 4cc9c46850e864d0de867c99aabb635a5fcd3f9b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144916"
---
# <a name="fatal-error-c1104"></a>Önemli hata C1104

libıd içeri aktarılırken önemli hata: ' Message '

Derleyici, bir tür kitaplığını içeri aktarırken bir sorun algıladı.  Örneğin, lııdıd içeren bir tür kitaplığı belirtemezsiniz ve ayrıca belirtebilirsiniz `no_registry` .

Daha fazla bilgi için bkz. [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

Aşağıdaki örnek C1104 oluşturacaktır:

```cpp
// C1104.cpp
#import "libid:11111111.1111.1111.1111.111111111111" version("4.0") lcid("9") no_registry auto_search   // C1104
```
