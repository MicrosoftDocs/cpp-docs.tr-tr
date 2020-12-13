---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3132'
title: Derleyici hatası C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: e81ddcb977342a687dce329239a590f90eca67ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177399"
---
# <a name="compiler-error-c3132"></a>Derleyici hatası C3132

' function-Parameter ': parametre dizileri yalnızca ' tek boyutlu yönetilen dizi ' türünde bir biçimsel bağımsız değişkene uygulanabilir

<xref:System.ParamArrayAttribute>Öznitelik, tek boyutlu bir dizi olmayan bir parametreye uygulandı.

Aşağıdaki örnek C3132 oluşturur:

```cpp
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```
