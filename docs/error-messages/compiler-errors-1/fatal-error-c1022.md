---
title: Önemli hata C1022
ms.date: 11/04/2016
f1_keywords:
- C1022
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
ms.openlocfilehash: 044ebbbe895677acf74977e56879c292486e18cb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383145"
---
# <a name="fatal-error-c1022"></a>Önemli hata C1022

#endif bekleniyor

Bir `#if`, `#ifdef`, veya `#ifndef` yönergesi sahip eşleşen `#endif` yönergesi. Her emin olması `#if`, `#ifdef`, veya `#ifndef` eşleşen bir `#endif`.

Aşağıdaki örnek, C1022 oluşturur:

```
// C1022.cpp
#define true 1

#if (true)
#else
#else    // C1022
```

Olası çözüm:

```
// C1022b.cpp
// compile with: /c
#define true 1

#if (true)
#else
#endif
```