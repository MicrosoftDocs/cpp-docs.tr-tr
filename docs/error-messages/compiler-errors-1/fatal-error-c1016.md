---
description: 'Daha fazla bilgi edinin: önemli hata C1016'
title: Önemli hata C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: e0f9a887c42c7006a31124446021ebee54225984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262418"
---
# <a name="fatal-error-c1016"></a>Önemli hata C1016

\#IDEF bir tanımlayıcı bekliyordu # ifndef bir tanımlayıcı bekliyordu

Koşullu derleme yönergesinin ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) veya `#ifndef` ) değerlendirmek için tanımlayıcısı yok. Hatayı gidermek için bir tanımlayıcı belirtin.

Aşağıdaki örnek C1016 oluşturur:

```cpp
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

Olası çözüm:

```cpp
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```
