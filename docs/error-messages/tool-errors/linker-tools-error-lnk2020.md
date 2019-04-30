---
title: Bağlayıcı Araçları Hatası LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 7290a90dfd92d84c4632e7f9dd38d36eccd4ac27
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386336"
---
# <a name="linker-tools-error-lnk2020"></a>Bağlayıcı Araçları Hatası LNK2020

Çözümlenmemiş belirteç 'belirteci

Tanımlanamayan bir dış hata benzeyen meta veri başvurusu olması dışında. Meta veriler, tüm işlevler ve veriler tanımlanması gerekir.

Çözmek için:

- Eksik işlev veya verileri tanımlamak veya

- Nesne dosyası ya da eksik işlevi veya verileri önceden tanımlandığı kitaplığı içerir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK2020 oluşturur.

```
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

## <a name="example"></a>Örnek

Yönetilen bir şablon türü bir değişken oluşturun, ancak türü de örneklemeyin LNK2020 de gerçekleşir.

Aşağıdaki örnek, LNK2020 oluşturur.

```
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```