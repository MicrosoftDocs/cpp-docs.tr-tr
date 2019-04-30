---
title: Önemli hata C1020
ms.date: 11/04/2016
f1_keywords:
- C1020
helpviewer_keywords:
- C1020
ms.assetid: 42f429e2-5e3b-4086-a10d-b99e032e51c5
ms.openlocfilehash: bdd7a6c87b0e00bd7bef174b8daf0e16cc488a5d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383158"
---
# <a name="fatal-error-c1020"></a>Önemli hata C1020

Beklenmeyen #endif

`#endif` Yönergesi sahip eşleşen `#if`, `#ifdef`, veya `#ifndef` yönergesi. Her emin olması `#endif` eşleşen yönergesi yok.

Aşağıdaki örnek, C1020 oluşturur:

```
// C1020.cpp
#endif     // C1020
```

Olası çözüm:

```
// C1020b.cpp
// compile with: /c
#if 1
#endif
```