---
title: Derleyici Hatası C2675 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2675
dev_langs:
- C++
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fb949f5d6ab5881b911bab89150ae13f47443fcf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33235675"
---
# <a name="compiler-error-c2675"></a>Derleyici Hatası C2675
birli 'işleci': 'type' değil tanımlamak bu işleci veya kabul edilebilir bir tür dönüşümünü önceden tanımlanmış işleci  
  
 C2675 de birli işleç kullanılarak ortaya çıkabilir ve türü için önceden tanımlanmış işleci işleci veya kabul edilebilir bir tür dönüşümünü tanımlamıyor. İşleç kullanmak için belirtilen tür için aşırı yükleme veya işleci tanımlandığı bir türe dönüştürme tanımlayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2675 oluşturur.  
  
```  
// C2675.cpp  
struct C {   
   C(){}  
} c;  
  
struct D {   
   D(){}  
   void operator-(){}  
} d;  
  
int main() {  
   -c;   // C2675  
   -d;   // OK  
}  
```