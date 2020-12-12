---
description: 'Daha fazla bilgi edinin: Derleyici Uyarısı (düzey 3) C4290'
title: Derleyici Uyarısı (düzey 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 771eb01c23778a716aee22ca747ea6473909a8bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344074"
---
# <a name="compiler-warning-level-3-c4290"></a>Derleyici Uyarısı (düzey 3) C4290

C++ özel durum belirtimi, bir işlevin __declspec (nothrow) olmadığını göstermek dışında yoksayıldı

Bir işlev, Visual C++ kabul etmeyen ancak uygulamadığından özel durum belirtimi kullanılarak bildirilmiştir. Derleme sırasında yoksayılan özel durum belirtimlerine sahip kodun, özel durum belirtimlerini destekleyen gelecek sürümlerde yeniden derlenmesi ve bağlanması gerekebilir.

Daha fazla bilgi için bkz. [özel durum belirtimleri (throw)](../../cpp/exception-specifications-throw-cpp.md) .

[Uyarı](../../preprocessor/warning.md) pragmasını kullanarak bu uyarıdan kaçınabilirsiniz:

```cpp
#pragma warning( disable : 4290 )
```

Aşağıdaki kod örneği C4290 oluşturur:

```cpp
// C4290.cpp
// compile with: /EHs /W3 /c
void f1(void) throw(int) {}   // C4290

// OK
void f2(void) throw() {}
void f3(void) throw(...) {}
```
