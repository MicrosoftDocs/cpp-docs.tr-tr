---
title: Derleyici Uyarısı (düzey 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: 9b38e9670157fd15dc7c4b6a96ced7ad40c43e34
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80186003"
---
# <a name="compiler-warning-level-1-c4606"></a>Derleyici Uyarısı (düzey 1) C4606

\#pragma warning: ' warning_number ' yoksayıldı; Kod Analizi uyarıları, uyarı düzeyleriyle ilişkili değil

Kod Analizi uyarıları için, yalnızca `error`, `once`ve `default` [Uyarı](../../preprocessor/warning.md) pragması ile desteklenir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4606 oluşturur.

```cpp
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```
