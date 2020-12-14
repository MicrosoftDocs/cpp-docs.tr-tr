---
description: 'Daha fazla bilgi edinin: önemli hata C1022'
title: Önemli hata C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: cd608aded29b4f3ebf329586ebc03ce2e325c970
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249769"
---
# <a name="fatal-error-c1022"></a>Önemli hata C1022

beklenen #endif

`#if`, `#ifdef` , Veya `#ifndef` yönergesinin eşleşen bir yönergesi yok `#endif` . Her birinin `#if` , veya eşleştirmesi olduğundan emin olun `#ifdef` `#ifndef` `#endif` .

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
