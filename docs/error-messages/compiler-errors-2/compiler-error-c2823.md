---
title: Derleyici Hatası C2823
ms.date: 11/04/2016
f1_keywords:
- C2823
helpviewer_keywords:
- C2823
ms.assetid: 982b1b35-1a7c-456e-b711-f80cfe2d571e
ms.openlocfilehash: 5f9b60499fd3c3bd5f06834e3c4f6482031066d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469764"
---
# <a name="compiler-error-c2823"></a>Derleyici Hatası C2823

> typedef şablon geçersizdir

Şablonları izin verilmiyor `typedef` tanımlar.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2823 oluşturur ve bunu çözmenin yollarından biri gösterilmektedir:

```cpp
// C2823.cpp
template<class T>
typedef struct x {
   T i;   // C2823 can't use T, specify data type and delete template
   int i;   // OK
} x1;
```