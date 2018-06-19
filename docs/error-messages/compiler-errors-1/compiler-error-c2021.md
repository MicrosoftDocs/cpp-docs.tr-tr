---
title: Derleyici Hatası C2021 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2021
dev_langs:
- C++
helpviewer_keywords:
- C2021
ms.assetid: 064f32e2-3794-48d5-9767-991003dcb36a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ae1c3640b4fbe5b1473c2e678406321f5533e586
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33167508"
---
# <a name="compiler-error-c2021"></a>Derleyici Hatası C2021
Beklenen üs değeri, 'character' değil  
  
 Kayan nokta sabiti üs kullanılan karakteri geçerli bir sayı değil. Aralıktaki bir üs kullandığınızdan emin olun.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2021 oluşturur:  
  
```  
// C2021.cpp  
float test1=1.175494351E;   // C2021  
```  
  
## <a name="example"></a>Örnek  
 Olası çözüm:  
  
```  
// C2021b.cpp  
// compile with: /c  
float test2=1.175494351E8;  
```