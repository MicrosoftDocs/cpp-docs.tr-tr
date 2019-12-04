---
title: Derleyici hatası C3622
ms.date: 11/04/2016
f1_keywords:
- C3622
helpviewer_keywords:
- C3622
ms.assetid: 02836f78-0cf2-4947-b87e-710187d81014
ms.openlocfilehash: 2adcee4cb20c39c39b06e0ac2087478cfe2d8937
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74740903"
---
# <a name="compiler-error-c3622"></a>Derleyici hatası C3622

' class ': ' anahtar sözcük ' olarak belirtilen bir sınıf başlatılamaz

[Soyut](../../extensions/abstract-cpp-component-extensions.md)olarak işaretlenmiş bir sınıfın örneğini oluşturma girişiminde bulunuldu. `abstract` olarak işaretlenen bir sınıf temel sınıf olabilir, ancak örneklenemez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3622 oluşturur.

```cpp
// C3622.cpp
// compile with: /clr
ref class a abstract {};

int main() {
   a aa;   // C3622
}
```
