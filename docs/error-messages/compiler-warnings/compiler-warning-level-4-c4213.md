---
title: "Derleyici Uyarısı (düzey 4) C4213 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4213
dev_langs: C++
helpviewer_keywords: C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: abe563bd91736c9dfb6c0efc6507763b03a329cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4213"></a>Derleyici Uyarısı (düzey 4) C4213
kullanılan standart olmayan uzantısı: l-değeri atama  
  
 Varsayılan Microsoft Uzantıları (/Ze), Atama ifadesinin sol tarafta atamaları kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// C4213.c  
// compile with: /W4  
void *a;  
void f()  
{  
   int   i[3];  
   a = &i;  
   *(( int * )a )++ = 3;  // C4213  
}  
  
int main()  
{  
}  
```  
  
 Tür atamaları ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).