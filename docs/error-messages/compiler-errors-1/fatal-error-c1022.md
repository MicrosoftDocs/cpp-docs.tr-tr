---
title: Önemli hata C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: b709d4bd855e38cb3721dec6d09b95ed02454def
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756883"
---
# <a name="fatal-error-c1022"></a>Önemli hata C1022

beklenen #endif

`#if`, `#ifdef`veya `#ifndef` yönergesinin eşleşen `#endif` yönergesi yok. Her `#if`, `#ifdef`veya `#ifndef` eşleşen bir `#endif`sahip olduğundan emin olun.

Aşağıdaki örnek C1022 oluşturur:

```cpp
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

Olası çözüm:

```cpp
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```
