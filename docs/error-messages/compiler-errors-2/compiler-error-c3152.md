---
title: Derleyici Hatası C3152 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3152
dev_langs:
- C++
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 93d1d73a5ab48ed992edafd8f6fe845e7e0f1561
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c3152"></a>Derleyici Hatası C3152
'oluşturmak': 'anahtar sözcüğü', yalnızca bir sınıf, yapı ya da sanal üye işlevi uygulanabilir  
  
 Belirli anahtar sözcükler yalnızca bir C++ sınıfa uygulanabilir.  
  
 Aşağıdaki örnek C3152 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C3152.cpp  
// compile with: /clr /c  
ref class C {  
   int (*pfn)() sealed;   // C3152  
   virtual int g() sealed;   // OK  
};  
```  
