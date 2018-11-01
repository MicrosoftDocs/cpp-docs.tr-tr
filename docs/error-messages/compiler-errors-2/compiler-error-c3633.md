---
title: Derleyici Hatası C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: 2d96a0e4f5f0b34c76f41058316c7f158f1a939d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624102"
---
# <a name="compiler-error-c3633"></a>Derleyici Hatası C3633

'member' yönetilen 'type' üyesi olarak tanımlanamaz

CLR başvuru sınıf veri üyeleri, bir POD harici C++ türünde olamaz.  Yalnızca bir CLR türü'nda POD yerel bir tür örneği oluşturabilir.  Örneğin, bir POD türü kopya oluşturucu veya bir atama işleci içeremez.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3633 oluşturur.

```
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
