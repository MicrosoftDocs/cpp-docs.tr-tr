---
title: Derleyici hatası C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 7ee7fb6e66ca9d5e09ad0eb445262c5f87d2060e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757078"
---
# <a name="compiler-error-c2491"></a>Derleyici hatası C2491

' Identifier ': dllimport işlevinin tanımına izin verilmiyor

Veriler, statik veri üyeleri ve işlevler `dllimport`s olarak bildirilemez ancak `dllimport`s olarak tanımlanmamıştır.

Bu sorunu onarmak için, işlevin tanımından `__declspec(dllimport)` belirticisini kaldırın.

Aşağıdaki örnek C2491 oluşturur:

```cpp
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```
