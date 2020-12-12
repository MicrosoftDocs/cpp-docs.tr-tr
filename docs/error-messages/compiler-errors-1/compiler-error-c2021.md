---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2021'
title: Derleyici hatası C2021
ms.date: 11/04/2016
f1_keywords:
- C2021
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
ms.openlocfilehash: 823d9c3d42f1df7bc6f6f398dafd804daef76110
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175644"
---
# <a name="compiler-error-c2021"></a>Derleyici hatası C2021

' karakter ' değil üs değeri bekleniyordu

Kayan nokta sabitinin üs değeri olarak kullanılan karakter geçerli bir sayı değil. Aralık içinde olan bir üs kullandığınızdan emin olun.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2021 oluşturur:

```cpp
// C2021.cpp
float test1=1.175494351E;   // C2021
```

Olası çözüm:

```cpp
// C2021b.cpp
// compile with: /c
float test2=1.175494351E8;
```
