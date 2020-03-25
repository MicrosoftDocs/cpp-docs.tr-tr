---
title: Derleyici hatası C2144
ms.date: 11/04/2016
f1_keywords:
- C2144
helpviewer_keywords:
- C2144
ms.assetid: 49f3959b-324f-4c06-9588-c0ecef5dc5b3
ms.openlocfilehash: b917c0a2c15aeb70222c948bce9a6fb275c91068
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80207252"
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
