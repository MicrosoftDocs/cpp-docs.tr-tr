---
title: Derleyici Hatası C2371 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2371
dev_langs:
- C++
helpviewer_keywords:
- C2371
ms.assetid: d383993d-05ef-4e35-8129-3b58a6f7b7b7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a3b26ca1ea591a740481ff1fb7d0936ff315790
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2371"></a>Derleyici Hatası C2371
'tanımlayıcısı': şemadaki; farklı temel türleri  
  
 Tanımlayıcı zaten bildirildi.  
  
 Aşağıdaki örnek C2371 oluşturur:  
  
```  
// C2371.cpp  
int main() {  
   int i;  
   float i;   // C2371, redefinition  
   float f;   // OK  
}  
```