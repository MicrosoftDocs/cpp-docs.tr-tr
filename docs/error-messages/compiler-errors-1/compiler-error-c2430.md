---
title: "Derleyici Hatası C2430 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2430
dev_langs:
- C++
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cc33ec719413d481c8994d3cab7def55e5fed658
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2430"></a>Derleyici Hatası C2430
birden fazla dizin 'tanımlayıcısı' kaydetme  
  
 Birden fazla kayıt ölçeklendirilir. Ölçeklendirilmiş dizin oluşturma derleyici destekler, ancak yalnızca bir kasa ölçeklendirebilirsiniz.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2430 oluşturur.  
  
```  
// C2430.cpp  
// processor: x86  
int main() {  
   _asm mov eax, [ebx*2+ecx*4] // C2430  
}  
```