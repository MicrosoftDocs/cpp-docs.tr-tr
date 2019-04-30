---
title: Derleyici Hatası C2678
ms.date: 11/04/2016
f1_keywords:
- C2678
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
ms.openlocfilehash: 9055210401e14eeb9fdb88266870ac8fe5cbd496
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62395397"
---
# <a name="compiler-error-c2678"></a>Derleyici Hatası C2678

İkili 'operator': 'type' türünde bir sol işleneni alan hiçbir işleç tanımlanmış (veya hiç kabul edilebilir dönüştürme yok)

İşlecini kullanmak için belirtilen tür için aşırı veya tanımlar işlecin tanımlandığı bir türe dönüştürmeyi gerekir.

## <a name="example"></a>Örnek

Sol işlenen const ile nitelenen ancak işleci const olmayan bir bağımsız değişken alan için tanımlanan C2678 oluşabilir.

Aşağıdaki örnek, C2678 oluşturur ve bu sorunun nasıl gösterir:

```
// C2678a.cpp
// Compile by using: cl /EHsc /W4 C2678a.cpp
struct Combo {
   int number;
   char letter;
};

inline Combo& operator+=(Combo& lhs, int rhs) {
   lhs.number += rhs;
   return lhs;
}

int main() {
   Combo const combo1{ 42, 'X' };
   Combo combo2{ 13, 'Z' };

   combo1 += 6; // C2678
   combo2 += 9; // OK - operator+= matches non-const Combo
}
```

## <a name="example"></a>Örnek

Üye işlevini çağırmadan önce yerel bir üye sabitlemeyin C2678 de ortaya çıkabilir.

Aşağıdaki örnek, C2678 oluşturur ve bu sorunun nasıl gösterir.

```
// C2678.cpp
// compile with: /clr /c
struct S { int _a; };

ref class C {
public:
   void M( S param ) {
      test = param;   // C2678

      // OK
      pin_ptr<S> ptest = &test;
      *ptest = param;
   }
   S test;
};
```
