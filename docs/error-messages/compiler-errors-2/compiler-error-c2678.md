---
title: Derleyici hatası C2678
ms.date: 11/04/2016
f1_keywords:
- C2678
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
ms.openlocfilehash: 390752d5d34685afc8b5fc5401fd75585bb48dd0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760341"
---
# <a name="compiler-error-c2678"></a>Derleyici hatası C2678

ikili ' işleç ': ' Type ' türünde bir sol taraftaki işlenen alan tanımlanmış işleç yok (veya kabul edilebilir dönüştürme yok)

İşlecini kullanmak için, belirtilen tür için onu tekrar yüklemelisiniz veya işlecin tanımlandığı bir türe dönüştürme tanımlamanız gerekir.

## <a name="example"></a>Örnek

C2678, sol işlenen const nitelikli olduğunda, ancak işleç const olmayan bir bağımsız değişken alacak şekilde tanımlandığında ortaya çıkabilir.

Aşağıdaki örnek C2678 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
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

C2678 bir üye işlevini çağırmadan önce yerel bir üyeyi sabitlemeyin, bu durum da oluşabilir.

Aşağıdaki örnek C2678 oluşturur ve nasıl düzeltileceğini gösterir.

```cpp
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
