---
title: Derleyici Hatası C2821 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2821
dev_langs:
- C++
helpviewer_keywords:
- C2821
ms.assetid: e8d71988-a968-4484-94db-e8c3bad74a4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 52525062a07c7c55dd323109be87667d9e0847d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46098231"
---
# <a name="compiler-error-c2821"></a>Derleyici Hatası C2821

'operator new' için ilk biçimsel parametre 'unsigned int' olmalıdır

İlk biçimsel parametresi [new işleci](../../standard-library/new-operators.md#op_new) imzasız olmalıdır `int`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2821 oluşturur:

```cpp
// C2821.cpp
// compile with: /c
void * operator new( /* unsigned int,*/ void * );   // C2821
void * operator new( unsigned int, void * );
```