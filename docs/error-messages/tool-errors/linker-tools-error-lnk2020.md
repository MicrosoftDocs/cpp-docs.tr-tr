---
title: Bağlayıcı araçları hatası LNK2020 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2020
dev_langs:
- C++
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90088d311bac7ee4ce59797d5dcbe148a24963f6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034973"
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