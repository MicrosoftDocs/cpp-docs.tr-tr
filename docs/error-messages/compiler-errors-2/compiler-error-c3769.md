---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3769'
title: Derleyici hatası C3769
ms.date: 11/04/2016
f1_keywords:
- C3769
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
ms.openlocfilehash: 5ed980ed75997637a59c6f2a0f864a20297e9a97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97291707"
---
# <a name="compiler-error-c3769"></a>Derleyici hatası C3769

' Type ': iç içe bir sınıf, hemen kapsayan sınıf ile aynı ada sahip olamaz

İç içe yerleştirilmiş bir sınıf, hemen kapsayan sınıf ile aynı ada sahip olamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C3769 oluşturur.

```cpp
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```
