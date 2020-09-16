---
title: Derleyici hatası C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: b2c5737a4442761cbaa84b532907e579eddb423d
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/16/2020
ms.locfileid: "90686071"
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
