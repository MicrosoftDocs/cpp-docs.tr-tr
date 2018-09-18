---
title: Derleyici Hatası C3769 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3769
dev_langs:
- C++
helpviewer_keywords:
- C3769
ms.assetid: 341675e1-7428-4da6-8275-1b2f0a70dacc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: da57a883bcf66535a531e98e23b5927d37cadccd
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46042239"
---
# <a name="compiler-error-c3769"></a>Derleyici Hatası C3769

'type': iç içe geçmiş bir sınıf kapsayan sınıf ile aynı ada sahip olamaz

İç içe geçmiş bir sınıf kapsayan sınıf ile aynı ada sahip olamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3769 oluşturur.

```
// C3769.cpp
// compile with: /c
class x {
   class x {};   // C3769
   class y {
      class x{};   // OK
   };
};
```