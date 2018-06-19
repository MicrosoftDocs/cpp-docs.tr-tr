---
title: Derleyici Uyarısı (Düzey 2) C4756 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4756
dev_langs:
- C++
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1b6f6cca331fdcd36c0917a9043b1f08ec4c2374
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33289691"
---
# <a name="compiler-warning-level-2-c4756"></a>Derleyici Uyarısı (Düzey 2) C4756
içinde sabit aritmetik taşma  
  
 Derleyici derleme sırasında sabit aritmetik yaparken bir özel durum oluşturdu.  
  
 Aşağıdaki örnek C4756 oluşturur:  
  
```  
// C4756.cpp  
// compile with: /W2 /Od  
int main()  
{  
   float f = 1e100+1e100;   // C4756  
}  
```