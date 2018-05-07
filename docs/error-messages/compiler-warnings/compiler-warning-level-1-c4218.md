---
title: Derleyici Uyarısı (düzey 1) C4218 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4218
dev_langs:
- C++
helpviewer_keywords:
- C4218
ms.assetid: d6c3cd90-4518-49e9-ae86-4ba9e2761d98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88b27af84c390760274bb20665eec4452c8e7072
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-warning-level-1-c4218"></a>Derleyici Uyarısı (düzey 1) C4218
kullanılan standart olmayan uzantısı: en az bir depolama sınıfı ya da türü belirtmeniz gerekir  
  
 Varsayılan Microsoft Uzantıları (/Ze), bir tür veya depolama sınıfı belirtmeden bir değişken bildirebilirsiniz. Varsayılan türdür `int`.  
  
## <a name="example"></a>Örnek  
  
```  
// C4218.c  
// compile with: /W4  
i;  // C4218  
  
int main()  
{  
}  
```  
  
 Bu tür bildirimleri ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).