---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2491'
title: Derleyici hatası C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 4fd12e30672d7045aa4a7506b35b845e8cd018c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283712"
---
# <a name="compiler-error-c2491"></a>Derleyici hatası C2491

' Identifier ': dllimport işlevinin tanımına izin verilmiyor

Veriler, statik veri üyeleri ve işlevler s olarak bildirilemez `dllimport` ancak s olarak tanımlanamaz `dllimport` .

Bu sorunu onarmak için, belirteci, `__declspec(dllimport)` işlevin tanımından kaldırın.

Aşağıdaki örnek C2491 oluşturur:

```cpp
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```
