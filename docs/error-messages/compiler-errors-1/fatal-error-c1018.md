---
title: Önemli hata C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 327bc0d5200fc348611da107257f2086063648fa
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383223"
---
# <a name="fatal-error-c1018"></a>Önemli hata C1018

Beklenmeyen #elif

`#elif` Yönergesi görünür dışında bir `#if`, `#ifdef`, veya `#ifndef` oluşturun. Kullanım `#elif` yalnızca bu yapıları biri içinde.

Aşağıdaki örnek, C1018 oluşturur:

```
// C1018.cpp
#elif      // C1018
#endif

int main() {}
```

Olası çözüm:

```
// C1018b.cpp
#if 1
#elif
#endif

int main() {}
```