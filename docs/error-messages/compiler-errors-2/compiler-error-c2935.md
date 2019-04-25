---
title: Derleyici Hatası C2935
ms.date: 11/04/2016
f1_keywords:
- C2935
helpviewer_keywords:
- C2935
ms.assetid: e11ef90d-0756-4e43-8a09-4974c6aa72a3
ms.openlocfilehash: f44a8060910b1aeeaa4b85d1df081a559e720df8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164897"
---
# <a name="compiler-error-c2935"></a>Derleyici Hatası C2935

'class': türü sınıf kimliği için genel bir işlev yeniden tanımlandı

Genel veya Şablon sınıfı, genel bir işlev kullanamazsınız.

Küme ayraçları yanlış eşleşirse bu hataya neden olabilir.

Aşağıdaki örnek, C2935 oluşturur:

```
// C2935.cpp
// compile with: /c
template<class T>
struct TC {};
void TC<int>() {}   // C2935

// OK
struct TC2 {};
void TC2() {}
```

C2935, genel türler kullanırken da meydana gelebilir:

```
// C2935b.cpp
// compile with: /clr /c
generic<class T>
ref struct GC { };
void GC<int>() {}   // C2935
void GC() {}   // OK
```