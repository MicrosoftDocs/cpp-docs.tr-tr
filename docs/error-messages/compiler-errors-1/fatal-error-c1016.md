---
title: Önemli hata C1016
ms.date: 11/04/2016
f1_keywords:
- C1016
helpviewer_keywords:
- C1016
ms.assetid: 33f45c3e-2d8f-43ad-a445-c412d1d54ce1
ms.openlocfilehash: 7463c6962817716611f3571e073712f374773fa7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62243867"
---
# <a name="fatal-error-c1016"></a>Önemli hata C1016

\##ifndef tanımlayıcı bir tanımlayıcı bekliyordu ifdef bekleniyor

Koşullu derleme yönergesi ([#ifdef](../../preprocessor/hash-ifdef-and-hash-ifndef-directives-c-cpp.md) veya `#ifndef`) değerlendirmek için hiçbir tanımlayıcı vardır. Hatayı gidermek için bir tanımlayıcı belirtin.

Aşağıdaki örnek, C1016 oluşturur:

```
// C1016.cpp
#ifdef   // C1016
#define FC1016
#endif

int main() {}
```

Olası çözüm:

```
// C1016b.cpp
#ifdef X
#define FC1016
#endif

int main() {}
```