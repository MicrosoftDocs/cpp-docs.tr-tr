---
title: Önemli hata C1022 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1022
dev_langs:
- C++
helpviewer_keywords:
- C1022
ms.assetid: edada720-dc73-49bc-bd93-a7945a316312
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4ddeea660515ea0a71e4807a34d2172413796046
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46036741"
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