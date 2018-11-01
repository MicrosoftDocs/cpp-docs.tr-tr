---
title: Derleyici Hatası C2937
ms.date: 11/04/2016
f1_keywords:
- C2937
helpviewer_keywords:
- C2937
ms.assetid: 95671ca3-79f7-4b56-a5f2-a92296da1629
ms.openlocfilehash: 8ad25dbcec4ee8a8ed49449cf9e64ebae4af1321
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50541017"
---
# <a name="compiler-error-c2937"></a>Derleyici Hatası C2937

'class': türü sınıf kimliği bir genel tür tanımı yeniden tanımlandı

Genel bir genel veya Şablon sınıfı kullanamazsınız `typedef`.

Aşağıdaki örnek, C2937 oluşturur:

```
// C2937.cpp
// compile with: /c
template<class T>
struct TC { };
typedef int TC<int>;   // C2937
typedef TC<int> c;   // OK
```

C2937, genel türler kullanırken da meydana gelebilir:

```
// C2937b.cpp
// compile with: /clr
generic<class T>
ref struct GC { };
typedef int GC<int>;   // C2937
typedef GC<int> xx;   // OK
```