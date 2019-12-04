---
title: Derleyici hatası C2386
ms.date: 11/04/2016
f1_keywords:
- C2386
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
ms.openlocfilehash: 1ac58d63498df32488c1a0743aa6ad9f7b77b7ca
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745115"
---
# <a name="compiler-error-c2386"></a>Derleyici hatası C2386

' symbol ': geçerli kapsamda bu ada sahip bir simge zaten var

Bir ad alanı diğer adı oluşturmaya çalıştınız, ancak seçtiğiniz ad zaten var.

Aşağıdaki örnek C2386 oluşturur:

```cpp
// C2386.cpp
namespace A {
   int k;
}

int i;
namespace i = A;   // C2386, i already exists
```
