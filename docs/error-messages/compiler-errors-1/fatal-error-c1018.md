---
description: 'Daha fazla bilgi edinin: önemli hata C1018'
title: Önemli hata C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 68b81406916ef358a73112c9f6f8b2370c627e54
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316420"
---
# <a name="fatal-error-c1018"></a>Önemli hata C1018

beklenmeyen #elif

`#elif`Yönerge `#if` , `#ifdef` , veya yapısı dışında görüntülenir `#ifndef` . `#elif`Bu yapılarından yalnızca biri içinde kullanın.

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
