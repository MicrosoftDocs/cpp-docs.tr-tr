---
title: Derleyici hatası C3266
ms.date: 11/04/2016
f1_keywords:
- C3266
helpviewer_keywords:
- C3266
ms.assetid: 7375c099-acb7-42f6-898d-57cfefa010b8
ms.openlocfilehash: 9122663108cafc8c73564379892e96978a90b26d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74754179"
---
# <a name="compiler-error-c3266"></a>Derleyici hatası C3266

' class ': sınıf oluşturucusunun ' void ' parametre listesi olmalıdır

/CLR programlama kullanan bir sınıftaki Sınıf oluşturucuları parametre alamaz.

Aşağıdaki örnek C3266 oluşturur:

```cpp
// C3266.cpp
// compile with: /clr

ref class X {
   static X(int i) { // C3266
   // try the following line instead
   // static X() {
   }
};

int main() {
}
```
