---
title: Derleyici hatası C2739
ms.date: 11/04/2016
f1_keywords:
- C2739
helpviewer_keywords:
- C2739
ms.assetid: 5b63e435-7631-43d7-805e-f2adefb7e517
ms.openlocfilehash: 18cece8d9630aa93e867329acc7cefea30da3286
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759665"
---
# <a name="compiler-error-c2739"></a>Derleyici hatası C2739

' number ': açık yönetilen veya WinRT dizisi boyutları 1 ile 32 arasında olmalıdır

Bir dizi boyutu 1 ile 32 arasında değildi.

Aşağıdaki örnek C2739 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2739.cpp
// compile with: /clr
int main() {
   array<int, -1>^a;   // C2739
   // try the following line instead
   // array<int, 2>^a;
}
```
