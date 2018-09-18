---
title: Derleyici Hatası C2084 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2084
dev_langs:
- C++
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 09ce703b6908257e37c2b7ff1b2714f1426f941f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46052120"
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