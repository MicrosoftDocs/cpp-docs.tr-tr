---
title: Derleyici Uyarısı (düzey 4) C4238 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4238
dev_langs:
- C++
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 06dbec01da8d1b47cb7b93c90a22ae5266e9b4c8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292444"
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