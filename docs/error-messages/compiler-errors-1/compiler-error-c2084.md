---
title: Derleyici hatası C2084
ms.date: 11/04/2016
f1_keywords:
- C2084
helpviewer_keywords:
- C2084
ms.assetid: 990b107f-3721-4851-ae8b-4b69a8c149ed
ms.openlocfilehash: f217e0b94e27c0f85879e80b3ae887cb4f76f486
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216368"
---
# <a name="compiler-error-c2084"></a>Derleyici hatası C2084

'*Function*' işlevinin bir gövdesi zaten var

İşlev zaten tanımlandı.

Visual Studio 2002 öncesi,

- Derleyici, aynı gerçek türe çözümlenen birden çok şablon uzmanlığını kabul eder, ancak ek tanımlar hiçbir şekilde kullanılamaz. Derleyici artık bu birden çok tanımı algılar.

- **`__int32`** ve **`int`** ayrı türler olarak kabul edildi. Derleyici artık **`__int32`** için bir eş anlamlı olarak davranır **`int`** . Bu, her ikisinde de bir işlev aşırı yüklenmişse **`__int32`** **`int`** ve bir hata veriyorsa derleyicinin birden çok tanımı algıladığı anlamına gelir.

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
