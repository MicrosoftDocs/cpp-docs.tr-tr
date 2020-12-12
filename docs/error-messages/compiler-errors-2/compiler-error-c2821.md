---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2821'
title: Derleyici hatası C2821
ms.date: 11/04/2016
f1_keywords:
- C2821
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
ms.openlocfilehash: c21c9dc0b1413292e1d73b6448ed008d6fc9a64d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194702"
---
# <a name="compiler-error-c2821"></a>Derleyici hatası C2821

' operator New ' için ilk biçimsel parametre ' unsigned int ' olmalıdır

[New işlecinin](../../standard-library/new-operators.md#op_new) ilk biçimsel parametresi işaretsiz olmalıdır **`int`** .

## <a name="example"></a>Örnek

Aşağıdaki örnek C2821 oluşturur:

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```
