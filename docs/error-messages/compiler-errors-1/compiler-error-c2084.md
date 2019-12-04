---
title: Derleyici hatası C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: 881ae051b2779fe674b31b64a7cbe7be7cf63705
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757897"
---
# <a name="compiler-error-c2084"></a>Derleyici hatası C2084

'*Function*' işlevinin bir gövdesi zaten var

İşlev zaten tanımlandı.

Visual Studio 2002 öncesi,

- Derleyici, aynı gerçek türe çözümlenen birden çok şablon uzmanlığını kabul eder, ancak ek tanımlar hiçbir şekilde kullanılamaz. Derleyici artık bu birden çok tanımı algılar.

- `__int32` ve `int` ayrı türler olarak değerlendirildi. Derleyici artık `__int32` `int`için bir eş anlamlı olarak değerlendirir. Bu, bir işlev hem `__int32` hem de `int` üzerinde aşırı yüklenmişse ve bir hata veriyorsa derleyicinin birden çok tanımı algıladığı anlamına gelir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2084 oluşturur:

```cpp
// C2084.cpp
void Func(int);
void Func(int) {}   // define function
void Func(int) {}   // C2084 second definition
```

Bu hatayı düzeltmek için, yinelenen tanımı kaldırın:

```cpp
// C2084b.cpp
// compile with: /c
void Func(int);
void Func(int) {}
```
