---
title: "Derleyici Uyarısı (düzey 4) C4205 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4205
dev_langs: C++
helpviewer_keywords: C4205
ms.assetid: 39b5108c-7230-41b4-b2fe-2293eb6aae28
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 989fd0a9ce2598e2e5ce8f96e4459b49d26a49e3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4205"></a>Derleyici Uyarısı (düzey 4) C4205
kullanılan standart olmayan uzantısı: işlevi kapsamında statik işlev bildirimi  
  
 Microsoft Uzantıları (/Ze) ile **statik** işlevleri başka bir işlev içinde bildirilebilir. İşlev, genel kapsam verilir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4205.c  
// compile with: /W4  
void func1()  
{  
   static int func2();  // C4205  
};  
  
int main()  
{  
}  
```  
  
 Bu tür başlatmaları ANSI Uyumluluğu altında geçersiz ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).