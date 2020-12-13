---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3904'
title: Derleyici hatası C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 0b1564e609586318d23b4204242f0cb39034c4fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144189"
---
# <a name="compiler-error-c3904"></a>Derleyici hatası C3904

' property_accessor ': sayı parametreleri belirtilmelidir

İçindeki parametre sayısını `get` ve `set` yöntemlerinizi Özellik boyutlarına göre denetleyin.

- Yöntem için parametrelerin sayısı, `get` özelliğin boyut sayısına eşit veya dizinlenmemiş özellikler için sıfır olmalıdır.

- Metodun parametre sayısı, `set` özelliğin boyut sayısından bir daha büyük olmalıdır.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md).

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C3904 oluşturur.

```cpp
// C3904.cpp
// compile with: /clr /c
ref class X {
   property int P {
      // set
      void set();   // C3904
      // try the following line instead
      // void set(int);

      // get
      int get(int, int);   // C3904
      // try the following line instead
      // int get();
   };
};
```

Aşağıdaki örnek C3904 oluşturur.

```cpp
// C3904b.cpp
// compile with: /clr /c
ref struct X {
   property int Q[double, double, float, float, void*, int] {
      // set
      void set(double, void*);   // C3904
      // try the following line instead
      // void set(double, double, float, float, void*, int, int);

      // get
      int get();   // C3904
      // try the following line instead
      // int get(double, double, float, float, void*, int);
   }
};
```
