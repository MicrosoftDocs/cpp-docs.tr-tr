---
title: Derleyici Hatası C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: a75330d26b0924e60f7e46d10d617341709d7e23
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58778292"
---
# <a name="compiler-error-c2144"></a>Derleyici Hatası C2144

> sözdizimi hatası: '*türü*'tarafından gelmelidir'*belirteci*'

Beklenen derleyici *belirteci* ve *türü* yerine.

Bu hata, bir eksik kapanış ayracı, sağ parantez veya noktalı virgül tarafından kaynaklanabilir.

C2144, boşluk karakterini içeren bir CLR anahtar sözcüğü bir makro oluşturmaya çalışırken de oluşabilir.

Tür iletme çalışıyorsanız C2144 de görebilirsiniz. Bkz: [tür iletme (C + +/ CLI)](../../extensions/type-forwarding-cpp-cli.md) daha fazla bilgi için.

## <a name="examples"></a>Örnekler

Aşağıdaki örnek, C2144 oluşturur ve bunu düzeltmek için bir yol gösterir:

```cpp
// C2144.cpp
// compile with: /clr /c
#define REF ref
REF struct MyStruct0;   // C2144

// OK
#define REF1 ref struct
REF1 MyStruct1;
```

Aşağıdaki örnek, C2144 oluşturur ve bunu düzeltmek için bir yol gösterir:

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