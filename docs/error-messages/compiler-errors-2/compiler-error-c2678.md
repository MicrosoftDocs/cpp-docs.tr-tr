---
title: Derleyici hatası C2678
ms.date: 11/04/2016
f1_keywords:
- C2678
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
ms.openlocfilehash: c8f5b06e6c2f9966d714f4a360525617dbff400f
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743184"
---
# <a name="compiler-error-c2678"></a>Derleyici hatası C2678

ikili ' işleç ': ' Type ' türünde bir sol taraftaki işlenen alan tanımlanmış işleç yok (veya kabul edilebilir dönüştürme yok)

İşlecini kullanmak için, belirtilen tür için onu tekrar yüklemelisiniz veya işlecin tanımlandığı bir türe dönüştürme tanımlamanız gerekir.

C2678, sol işlenen const nitelikli olduğunda, ancak işleç const olmayan bir bağımsız değişken alacak şekilde tanımlandığında ortaya çıkabilir.

## <a name="examples"></a>Örnekler

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
