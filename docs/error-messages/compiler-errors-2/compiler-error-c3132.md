---
title: Derleyici Hatası C3132
ms.date: 11/04/2016
f1_keywords:
- C3132
helpviewer_keywords:
- C3132
ms.assetid: d54a3d12-336a-4ed0-ad4e-43cddac33b5e
ms.openlocfilehash: a4c6ce8005aecd094c57b3dbda5c95565deecb95
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519808"
---
# <a name="compiler-error-c3132"></a>Derleyici Hatası C3132

'işlev parametresi': parametre dizileri yalnızca 'single-dimensional yönetilen array' türündeki biçimsel bağımsız değişken için uygulanabilir

[ParamArray](https://msdn.microsoft.com/library/system.paramarrayattribute.aspx) öznitelik, bir tek boyutlu dizi olmayan bir parametre uygulandı.

Aşağıdaki örnek, C3132 oluşturur:

```
// C3132.cpp
// compile with: /clr /c
using namespace System;
void f( [ParamArray] Int32[,] );   // C3132
void g( [ParamArray] Int32[] );   // C3132

void h( [ParamArray] array<Char ^> ^ MyArray );   // OK
```