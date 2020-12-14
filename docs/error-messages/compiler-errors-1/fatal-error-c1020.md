---
description: 'Daha fazla bilgi edinin: önemli hata C1020'
title: Önemli hata C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: 444da85bddf65533eb5ae37278085664efeae7ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316368"
---
# <a name="fatal-error-c1020"></a>Önemli hata C1020

beklenmeyen #endif

`#endif`Yönergede eşleşen `#if` , `#ifdef` veya `#ifndef` yönergesi yok. Her birinin `#endif` eşleşen bir yönergesine sahip olduğundan emin olun.

Aşağıdaki örnek C1020 oluşturur:

```cpp
// C1020.cpp
#endif     // C1020
```

Olası çözüm:

```cpp
// C1020b.cpp
// compile with: /c
#if 1
#endif
```
