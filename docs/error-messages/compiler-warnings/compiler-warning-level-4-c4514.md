---
title: "Derleyici Uyarısı (düzey 4) C4514 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4514
dev_langs: C++
helpviewer_keywords: C4514
ms.assetid: cdae966a-9cd4-4e31-af30-2a014e68f614
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 888a8109495286c9bc1bfe80e55f66b3b861e21c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4514"></a>Derleyici Uyarısı (düzey 4) C4514
'function': başvurulmayan satır içi işlev kaldırıldı  
  
 İyileştirici çağrılmaz bir satır içi işlev kaldırıldı.  
  
 Varsayılan olarak bu uyarı kapalıdır. Bkz: [derleyici uyarıları emin olduğunuz kapalı varsayılan](../../preprocessor/compiler-warnings-that-are-off-by-default.md) daha fazla bilgi için.  
  
 Aşağıdaki örnek C4514 oluşturur:  
  
```  
// C4514.cpp  
// compile with: /W4  
#pragma warning(default : 4514)  
class A  
{  
   public:  
      void func()   // C4514, remove the function to resolve  
      {  
      }  
};  
  
int main()  
{  
}  
```