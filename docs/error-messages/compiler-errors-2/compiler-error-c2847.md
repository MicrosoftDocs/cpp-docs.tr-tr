---
title: Derleyici hatası C2847
ms.date: 11/04/2016
f1_keywords:
- C2847
helpviewer_keywords:
- C2847
ms.assetid: 9ad9a0e0-8b16-49d9-a5be-f8eda2372aa9
ms.openlocfilehash: b8b31dc461c1d589151701c6946f6ac1a95c5517
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738992"
---
# <a name="compiler-error-c2847"></a>Derleyici hatası C2847

Managed veya WinRT türü ' class ' öğesine sizeof uygulanamıyor

[Sizeof](../../cpp/sizeof-operator.md) işleci, derleme zamanında bir nesnenin değerini alır. Yönetilen veya WinRT sınıfının, arabiriminin veya değer türünün boyutu dinamiktir, bu nedenle derleme zamanında tanınamaz.

Örneğin, aşağıdaki örnek C2847 oluşturur:

```cpp
// C2847.cpp
// compile with: /clr
ref class A {};

int main() {
   A ^ xA = gcnew A;
   sizeof(*xA);   // C2847 cannot use sizeof on managed object
}
```
