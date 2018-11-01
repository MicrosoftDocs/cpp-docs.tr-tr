---
title: Derleyici Hatası C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 0bd9193d6e305a4b6c6851ef2524a68ecc056816
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565717"
---
# <a name="compiler-error-c2008"></a>Derleyici Hatası C2008

'character': Makro tanımında beklenmiyor

Hemen makro adı karakteri görüntülenir. Hatayı gidermek için olmalıdır bir boşluk sonra makro adı.

Aşağıdaki örnek, C2008 oluşturur:

```
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

Olası çözüm:

```
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```