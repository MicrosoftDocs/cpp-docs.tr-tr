---
title: Derleyici Uyarısı (düzey 3) C4290
ms.date: 11/04/2016
f1_keywords:
- C4290
helpviewer_keywords:
- C4290
ms.assetid: d1c6d85b-28e0-4a1f-9d48-23593337a6fb
ms.openlocfilehash: 5970aa439a450bda4c1a2036da299d5c3cfbdb7a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80198906"
---
# <a name="compiler-warning-level-3-c4290"></a>Derleyici Uyarısı (düzey 3) C4290

C++bir işlevin __declspec (nothrow) olmadığını göstermek dışında özel durum belirtimi yoksayıldı

Bir işlev, görselin C++ kabul ettiği ancak uygulamadığından özel durum belirtimi kullanılarak bildirilmiştir. Derleme sırasında yoksayılan özel durum belirtimlerine sahip kodun, özel durum belirtimlerini destekleyen gelecek sürümlerde yeniden derlenmesi ve bağlanması gerekebilir.

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
