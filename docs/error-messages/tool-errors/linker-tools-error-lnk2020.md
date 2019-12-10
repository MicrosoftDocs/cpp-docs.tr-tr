---
title: Bağlayıcı Araçları Hatası LNK2020
ms.date: 11/04/2016
f1_keywords:
- LNK2020
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
ms.openlocfilehash: 9c6be2548e277af08f1069a70b26cd761db835bc
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988766"
---
# <a name="linker-tools-error-lnk2020"></a>Bağlayıcı Araçları Hatası LNK2020

çözümlenmemiş belirteç ' token '

Başvurunun meta veriler üzerinden olması dışında tanımsız bir dış hataya benzer. Meta verilerde, tüm işlevler ve verilerin tanımlanması gerekir.

Bunu çözmek için:

- Eksik işlevi veya verileri tanımlayın veya

- Eksik işlevin veya verilerin zaten tanımlandığı nesne dosyasını veya kitaplığını dahil edin.

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK2020 oluşturur.

```cpp
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

Ayrıca, yönetilen şablon türünde bir değişken oluşturursanız, ancak türünü de örneklemeyin, LNK2020 de gerçekleşir.

Aşağıdaki örnek LNK2020 oluşturur.

```cpp
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
