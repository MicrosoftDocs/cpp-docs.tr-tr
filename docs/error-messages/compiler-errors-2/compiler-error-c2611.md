---
title: Derleyici hatası C2611
ms.date: 11/04/2016
f1_keywords:
- C2611
helpviewer_keywords:
- C2611
ms.assetid: 3f2d5253-f24f-4724-83d0-6b2aa6a4e551
ms.openlocfilehash: 345a942b0d0c6475a2087717454404685e8fb320
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737861"
---
# <a name="compiler-error-c2611"></a>Derleyici hatası C2611

' token ': ' ~ ' geçersiz (tanımlayıcı bekleniyor)

Belirteç bir tanımlayıcı değil.

Aşağıdaki örnek C2611 oluşturur:

```cpp
// C2611.cpp
// compile with: /c
class C {
   C::~operator int();   // C2611
   ~C();   // OK
};
```
