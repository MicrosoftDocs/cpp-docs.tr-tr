---
title: Önemli hata C1019
ms.date: 11/04/2016
f1_keywords:
- C1019
helpviewer_keywords:
- C1019
ms.assetid: c4f8968b-bc62-4200-b3ca-69d06c163236
ms.openlocfilehash: 2d8e63510b762b0de0cda50ab7a03b773dfb949a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383132"
---
# <a name="fatal-error-c1019"></a>Önemli hata C1019

Beklenmeyen #else

`#else` Yönergesi görünür dışında bir `#if`, `#ifdef`, veya `#ifndef` oluşturun. Kullanım `#else` yalnızca bu yapıları biri içinde.

Aşağıdaki örnek, C1019 oluşturur:

```
// C1019.cpp
#else   // C1019
#endif

int main() {}
```

Olası çözüm:

```
// C1019b.cpp
#if 1
#else
#endif

int main() {}
```