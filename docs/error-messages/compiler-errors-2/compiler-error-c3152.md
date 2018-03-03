---
title: "Derleyici Hatası C3152 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3152
dev_langs:
- C++
helpviewer_keywords:
- C3152
ms.assetid: 4ee6e2cd-5d19-4b73-833d-765c35797e4b
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5e375586f6047ac0fef846cd6bf7b4f1e68d330
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
