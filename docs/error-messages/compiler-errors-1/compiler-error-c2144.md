---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2144'
title: Derleyici hatası C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: 172ccb897937008aa305616eea19f234dfc6a3bd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97235508"
---
# <a name="compiler-error-c2144"></a>Derleyici hatası C2144

> sözdizimi hatası: '*Type*' öncesinde '*token*' gelmelidir

Derleyici *belirteç* bekliyordu ve bunun yerine *tür* buldu.

Bu hata, eksik bir kapatma ayracı, sağ parantez veya noktalı virgülden kaynaklanıyor olabilir.

C2144, boşluk karakteri içeren bir CLR anahtar sözcüğünden makro oluşturmaya çalışırken da oluşabilir.

Tür iletme yapmaya çalışıyorsanız C2144 de görebilirsiniz. Daha fazla bilgi için bkz. [tür iletme (C++/CLI)](../../extensions/type-forwarding-cpp-cli.md) .

## <a name="examples"></a>Örnekler

Aşağıdaki örnek C2144 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Aşağıdaki örnek C2144 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2144_2.cpp
// compile with: /clr /c
ref struct X {

   property double MultiDimProp[,,] {   // C2144
   // try the following line instead
   // property double MultiDimProp[int , int, int] {
      double get(int, int, int) { return 1; }
      void set(int i, int j, int k, double l) {}
   }

   property double MultiDimProp2[] {   // C2144
   // try the following line instead
   // property double MultiDimProp2[int] {
      double get(int) { return 1; }
      void set(int i, double l) {}
   }
};
```
