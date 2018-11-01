---
title: Derleyici Uyarısı (Düzey 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: c585294686298a1197d437d41a0d541f1268985f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512742"
---
# <a name="compiler-warning-level-3-c4290"></a>Derleyici Uyarısı (Düzey 3) C4290

C++ özel durum belirtimi bir işlevin dışında göz ardı __declspec(nothrow) olmadığını

Visual C++ kabul eder, ancak uygulamayan özel durum belirtimi kullanılarak bildirilen bir işlev. Kod özel durum ile derleme sırasında yok sayılır belirtimleri derlenmesi gerekebilir ve bağlı olarak gelecekte özel durum belirtimleri destekleyen sürümler yeniden kullanılabilir.

Daha fazla bilgi için [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md) .

Bu uyarı kullanarak kaçınabilirsiniz [uyarı](../../preprocessor/warning.md) pragma:

```
#pragma warning( disable : 4290 )
```

Aşağıdaki kod örneği C4290 oluşturur:

```
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```