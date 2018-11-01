---
title: Derleyici Hatası C2710
ms.date: 11/04/2016
f1_keywords:
- C2710
helpviewer_keywords:
- C2710
ms.assetid: a2a6bb5b-86ad-4a6c-acd0-e2bef8464e0e
ms.openlocfilehash: 54d501d43652bb8e54092d44042a9525ef6f708f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618952"
---
# <a name="compiler-error-c2710"></a>Derleyici Hatası C2710

'oluşturmak': '__declspec(modifier)' yalnızca işaretçi döndüren bir işleve uygulanabilir

Dönüş değeri olan bir işaretçi bir işlev, yalnızca yapıdır `modifier` uygulanabilir.

Aşağıdaki örnek, C2710 oluşturur:

```
// C2710.cpp
__declspec(restrict) void f();   // C2710
// try the following line instead
__declspec(restrict) int * g();
```