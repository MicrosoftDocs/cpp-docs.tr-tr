---
title: Derleyici Hatası C3857
ms.date: 11/04/2016
f1_keywords:
- C3857
helpviewer_keywords:
- C3857
ms.assetid: 9f746d1e-9708-4945-bc29-3150d5371d3c
ms.openlocfilehash: 1270d09c870bfdf9f390d6afb1625ad3e99e01a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265444"
---
# <a name="compiler-error-c3857"></a>Derleyici Hatası C3857

'type': birden çok tür parametre listeleri izin verilmez

Bir şablon büyük veya genel verilmeyen aynı türü için belirtildi.

Aşağıdaki örnek, C3857 oluşturur:

```
// C3857.cpp
template <class T, class TT>
template <class T2>    // C3857
struct B {};
```

Olası çözüm:

```
// C3857b.cpp
// compile with: /c
template <class T, class TT, class T2>
struct B {};
```

C3857, genel türler kullanırken da meydana gelebilir:

```
// C3857c.cpp
// compile with: /clr
generic <typename T>
generic <typename U>
ref class GC;   // C3857
```

Olası çözüm:

```
// C3857d.cpp
// compile with: /clr /c
generic <typename U>
ref class GC;
```