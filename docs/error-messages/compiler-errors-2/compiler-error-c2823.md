---
title: Derleyici hatası C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: c277437bdc4622e7ae8a63eb9b0a553e0079bc02
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225390"
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
