---
title: "Derleyici Uyarısı (Düzey 2) C4094 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4094
dev_langs:
- C++
helpviewer_keywords:
- C4094
ms.assetid: e68929fb-3a1c-4be7-920b-d5f79f534f99
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27b2d664996ee3db1c1b505eb8db0346d683ff8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-2-c4094"></a>Derleyici Uyarısı (Düzey 2) C4094
Etiketlenmemiş 'belirteci' simge bildirilen  
  
 Derleyici etiketlenmemiş yapısı, UNION veya sınıfı kullanarak boş bir bildirimi algıladı. Bildirim göz ardı edilir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4094.cpp  
// compile with: /W2  
struct  
{  
};   // C4094  
  
int main()  
{  
}  
```  
  
 Bu koşul ANSI Uyumluluğu altında bir hata oluşturur ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).