---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4606'
title: Derleyici Uyarısı (düzey 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: b347be103d2a84dba2143861cb35b67f3d38fb9c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341743"
---
# <a name="compiler-warning-level-1-c4606"></a>Derleyici Uyarısı (düzey 1) C4606

\#pragma warning: ' warning_number ' yoksayıldı; Kod Analizi uyarıları, uyarı düzeyleriyle ilişkili değil

Kod Analizi uyarıları için, yalnızca `error` , `once` , ve `default` [Uyarı](../../preprocessor/warning.md) pragması ile desteklenir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4606 oluşturur.

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
