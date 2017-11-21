---
title: "Derleyici Uyarısı (düzey 4) C4220 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4220
dev_langs: C++
helpviewer_keywords: C4220
ms.assetid: aba18868-825f-4763-9af6-3296406a80e4
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82e921ecbb19ff705c7e2341d39d07991d6cb30a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4220"></a>Derleyici Uyarısı (düzey 4) C4220
Kalan parametreleri VarArgs eşleşir  
  
 Varsayılan Microsoft Uzantıları (/Ze) altında bir işlev işaretçisi benzer, ancak değişken, bağımsız değişkenlere sahip bir işlev işaretçisi eşleşir.  
  
## <a name="example"></a>Örnek  
  
```  
// C4220.c  
// compile with: /W4  
  
int ( *pFunc1) ( int a, ... );  
int ( *pFunc2) ( int a, int b);  
  
int main()  
{  
   if ( pFunc1 != pFunc2 ) {};  // C4220  
}  
```  
  
 Bu tür işaretçileri ANSI Uyumluluğu altında eşleşmiyor ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).