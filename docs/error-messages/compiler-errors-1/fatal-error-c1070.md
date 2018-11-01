---
title: Önemli hata C1070
ms.date: 11/04/2016
f1_keywords:
- C1070
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
ms.openlocfilehash: 7e156a230ce9550b65d1b8775947fc7294c15377
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50445025"
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