---
title: Önemli hata C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 3273288f1d60fad840fd8e9c459ce5d209ddb6a4
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756935"
---
# <a name="fatal-error-c1018"></a>Önemli hata C1018

beklenmeyen #elif

`#elif` yönergesi `#if`, `#ifdef`veya `#ifndef` yapısı dışında görüntülenir. Bu yapılarından yalnızca biri içinde `#elif` kullanın.

Aşağıdaki örnek C1018 oluşturur:

```cpp
// C1018.cpp
#elif      // C1018
#endif

int main() {}
```

Olası çözüm:

```cpp
// C1018b.cpp
#if 1
#elif
#endif

int main() {}
```
