---
title: Derleyici Uyarısı (düzey 1) C4606 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4606
dev_langs:
- C++
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bf9f0a954b48e2c8bd036651efa3e8a3e65b8e68
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33279464"
---
# <a name="compiler-warning-level-1-c4606"></a>Derleyici Uyarısı (düzey 1) C4606
\#pragma uyarısı: 'warning_number göz ardı;' Kod çözümleme uyarıları uyarı düzeyleri ile ilişkili değil  
  
 Kod çözümleme uyarıları, yalnızca için `error`, `once`, ve `default` ile desteklenen [uyarı](../../preprocessor/warning.md) pragması.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4606 oluşturur.  
  
```  
// C4606.cpp  
// compile with: /c /W1  
#pragma warning(1: 6001)   // C4606  
#pragma warning(once: 6001)   // OK  
```