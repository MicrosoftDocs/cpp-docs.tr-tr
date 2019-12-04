---
title: Derleyici hatası C2745
ms.date: 11/04/2016
f1_keywords:
- C2745
helpviewer_keywords:
- C2745
ms.assetid: a1c45f13-7667-4678-aa16-265304a449a1
ms.openlocfilehash: 5fe19bcf55c743bb3e35d1ca9ae28d2b08dcbd89
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759015"
---
# <a name="compiler-error-c2745"></a>Derleyici hatası C2745

' belirteç ': Bu belirteç bir tanımlayıcıya dönüştürülemez

Tanımlayıcılar, yasal karakterlerden oluşmalıdır.

Aşağıdaki örnek C2745 oluşturur:

```cpp
// C2745.cpp
// compile with: /clr
int main() {
   int __identifier([));   // C2745
}
```
