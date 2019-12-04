---
title: Derleyici hatası C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 24463abcf123fda285356c86e3394d7274f2f6c8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751046"
---
# <a name="compiler-error-c2021"></a>Derleyici hatası C2021

' karakter ' değil üs değeri bekleniyordu

Kayan nokta sabitinin üs değeri olarak kullanılan karakter geçerli bir sayı değil. Aralık içinde olan bir üs kullandığınızdan emin olun.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2021 oluşturur:

```cpp
// C2021.cpp
float test1=1.175494351E;   // C2021
```

## <a name="example"></a>Örnek

Olası çözüm:

```cpp
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```
