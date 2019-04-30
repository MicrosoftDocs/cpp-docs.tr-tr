---
title: Derleyici Hatası C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 9aaf3a88e63234dfb842e4b48afd6e55595e96ca
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62391926"
---
# <a name="compiler-error-c2084"></a>Derleyici Hatası C2084

İşlev '*işlevi*' bir gövdesi zaten var

İşlev zaten tanımlandı.

Visual Studio 2002 önce Visual C++ sürümlerinde

- Derleyici, ek tanımları hiçbir zaman kullanılabilir olacak olsa da aynı gerçek türüne çözümlenen birden fazla şablon uzmanlıkları kabul eder. Derleyici artık bu birden çok tanımları algılar.

- `__int32` ve `int` ayrı türleri olarak kabul. Derleyici artık işler `__int32` eşanlamlısı olarak `int`. Bir işlev hem de aşırı yüklüyse derleyici birden çok tanım algılar yani `__int32` ve `int` ve bir hata verir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2084 oluşturur:

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

Bu hatayı düzeltmek için yinelenen tanımları kaldırın:

```
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```