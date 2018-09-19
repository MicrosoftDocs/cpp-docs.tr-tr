---
title: Derleyici Uyarısı (Düzey 3) C4290 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4290
dev_langs:
- C++
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3a6f09d8f3396381f34a0fbe3c7150b5948cee01
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46015983"
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