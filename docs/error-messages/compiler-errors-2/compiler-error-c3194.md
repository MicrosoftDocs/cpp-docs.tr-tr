---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3194'
title: Derleyici hatası C3194
ms.date: 11/04/2016
f1_keywords:
- C3194
helpviewer_keywords:
- C3194
ms.assetid: 49d3ffc6-eff6-4b46-865b-18811692a8bb
ms.openlocfilehash: 7513b9d4964b6eb0024c3b51480f188243bf2637
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174045"
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
