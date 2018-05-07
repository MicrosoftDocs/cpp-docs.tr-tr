---
title: Derleyici Hatası C2430 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2430
dev_langs:
- C++
helpviewer_keywords:
- C2430
ms.assetid: 07c20f76-63e1-4d22-b2a9-98b0d45c5cac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 56e1817cf9c5291114af0d94f92e01071d0f7190
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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