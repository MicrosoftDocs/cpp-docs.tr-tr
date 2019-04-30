---
title: Derleyici Hatası C3904
ms.date: 11/04/2016
f1_keywords:
- C3904
helpviewer_keywords:
- C3904
ms.assetid: 08297605-e4f2-4c6c-b637-011f1fd40631
ms.openlocfilehash: 4675bf95012c8e6662d7dba281c38ed2d684c448
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62406775"
---
# <a name="compiler-error-c3904"></a>Derleyici Hatası C3904

'property_accessor': parametre sayısı belirtmelidir

Parametre sayısı denetleyin, `get` ve `set` yöntemleri özellik boyutlarına göre.

- İçin parametre sayısı `get` yöntemi özelliğinin boyut sayısına eşit veya dizinlenmemiş özellikleri için sıfır olması gerekir.

- Parametrelerinin sayısı `set` yöntemi olmalı boyut özelliğinin sayısından daha fazla.

Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3904 oluşturur.

```
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

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3904 oluşturur.

```
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