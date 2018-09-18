---
title: Önemli hata C1070 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1070
dev_langs:
- C++
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7e871b69bb189140a4001d574736a255eefaf61
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46055630"
---
# <a name="fatal-error-c1070"></a>Önemli hata C1070

eşleşmeyen #if / #endif çifti 'filename' dosya

Bir `#if`, `#ifdef`, veya `#ifndef` yönergesi, karşılık gelen içeriyor `#endif`.

Aşağıdaki örnek, C1070 oluşturur:

```
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

Olası çözüm:

```
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```