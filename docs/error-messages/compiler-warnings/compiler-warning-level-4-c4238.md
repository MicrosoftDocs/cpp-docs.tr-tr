---
title: "Derleyici Uyarısı (düzey 4) C4238 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4238
dev_langs: C++
helpviewer_keywords: C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8e8e52868d97d31243f92307e9bfd158c818c2f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4238"></a>Derleyici Uyarısı (düzey 4) C4238
kullanılan standart olmayan uzantısı: lvalue kullanılan sınıf rvalue  
  
 Visual C++, Microsoft uzantıları önceki sürümleriyle uyumluluk için (**/Ze**) bir rvalue bağlamda adresini bu örtük veya açık olarak yararlanırken bir sınıf türü kullanmanızı sağlar. Aşağıdaki örnekte, gibi bazı durumlarda bu tehlikeli olabilir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4238.cpp  
// compile with: /W4 /c  
struct C {  
   C() {}  
};  
  
C * pC = &C();   // C4238  
```  
  
 Bu kullanım ANSI Uyumluluğu altında bir hataya neden olur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).