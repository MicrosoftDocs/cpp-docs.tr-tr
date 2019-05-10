---
title: Derleyici Hatası C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 0f7e049bc3f96e0a8e2b0a8cd306afeff52f7a5f
ms.sourcegitcommit: 7d64c5f226f925642a25e07498567df8bebb00d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2019
ms.locfileid: "65447333"
---
# <a name="compiler-error-c2084"></a>Derleyici Hatası C2084

İşlev '*işlevi*' bir gövdesi zaten var

İşlev zaten tanımlandı.

Visual Studio 2002 önce

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