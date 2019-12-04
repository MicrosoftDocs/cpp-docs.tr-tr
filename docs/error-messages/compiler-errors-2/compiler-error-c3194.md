---
title: Derleyici hatası C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 83c07da5383740ca14c9b9de6224f47cf844d5fa
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757650"
---
# <a name="compiler-error-c3194"></a>Derleyici hatası C3194

' üye ': bir değer türünün atama işleci olamaz

Bir değer sınıfında bir kopya Oluşturucusu veya kopya atama işleci gibi derleyicinin otomatik olarak çağrılmasını gerektiren özel üye işlevleri desteklenmez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3194 oluşturur.

```cpp
// C3194.cpp
// compile with: /clr /c
value struct MyStruct {
   MyStruct& operator= (const MyStruct& i) { return *this; }   // C3194
};

ref struct MyStruct2 {
   MyStruct2% operator= (const MyStruct2% i) { return *this; }   // OK
};
```
