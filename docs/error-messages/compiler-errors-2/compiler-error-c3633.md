---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3633'
title: Derleyici hatası C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: caf89e2297bb4e9d62be76699b153f013095fa34
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239265"
---
# <a name="compiler-error-c3633"></a>Derleyici hatası C3633

yönetilen ' Type ' üyesi olarak ' Member ' tanımlanamıyor

CLR başvuru sınıfı veri üyeleri POD olmayan bir C++ türü olamaz.  CLR türünde yalnızca POD yerel türü oluşturabilirsiniz.  Örneğin, POD türü bir kopya Oluşturucusu veya atama işleci içeremez.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3633 oluşturur.

```cpp
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
