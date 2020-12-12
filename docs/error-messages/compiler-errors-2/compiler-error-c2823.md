---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2823'
title: Derleyici hatası C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 57dacaf144f23a1e8486d6a2849fffce0ff8be52
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194676"
---
# <a name="compiler-error-c2823"></a>Derleyici hatası C2823

> TypeDef şablonu geçersiz

Tanımlarda şablonlara izin verilmez **`typedef`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2823 oluşturur ve bunu çözmek için bir yol gösterir:

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```
