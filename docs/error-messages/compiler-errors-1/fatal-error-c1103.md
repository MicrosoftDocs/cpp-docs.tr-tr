---
description: 'Daha fazla bilgi edinin: önemli hata C1103'
title: Önemli hata C1103
ms.date: 11/04/2016
f1_keywords:
- C1103
helpviewer_keywords:
- C1103
ms.assetid: 9d276939-9c47-4235-9d20-76b8434f9731
ms.openlocfilehash: 7e49d4f4420fc202f54a580c194244d24a4d181c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144930"
---
# <a name="fatal-error-c1103"></a>Önemli hata C1103

ProgID içeri aktarılırken önemli hata: ' Message '

Derleyici, bir tür kitaplığını içeri aktarırken bir sorun algıladı.  Örneğin, ProgID içeren bir tür kitaplığı belirtemezsiniz ve de belirtebilirsiniz `no_registry` .

Daha fazla bilgi için bkz. [#import yönergesi](../../preprocessor/hash-import-directive-cpp.md).

Aşağıdaki örnek C1103 oluşturacaktır:

```cpp
// C1103.cpp
#import "progid:a.b.id.1.5" no_registry auto_search   // C1103
```
