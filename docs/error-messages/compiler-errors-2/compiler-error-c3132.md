---
title: Derleyici Hatası C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: 1a97e04747cb92909380e66d1f4ea8ca62183054
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62349886"
---
# <a name="compiler-error-c3132"></a>Derleyici Hatası C3132

'işlev parametresi': parametre dizileri yalnızca 'single-dimensional yönetilen array' türündeki biçimsel bağımsız değişken için uygulanabilir

<xref:System.ParamArrayAttribute> Öznitelik, bir tek boyutlu dizi olmayan bir parametre uygulandı.

Aşağıdaki örnek, C3132 oluşturur:

```
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```