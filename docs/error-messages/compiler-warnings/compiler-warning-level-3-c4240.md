---
title: "Derleyici Uyarısı (Düzey 3) C4240 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4240
dev_langs: C++
helpviewer_keywords: C4240
ms.assetid: a2657cdb-18e1-493f-882b-4e10c0bca71d
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eb26996ce68a29126292923ebe27e3dcfefd8f7f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-3-c4240"></a>Derleyici Uyarısı (Düzey 3) C4240
kullanılan standart olmayan uzantısı: erişim için 'şimdi 'erişim belirticisi', daha önce onu olarak tanımlanan classname' tanımlandığı 'erişim belirteci' olmalıdır  
  
 ANSI Uyumluluğu altında ([/Za](../../build/reference/za-ze-disable-language-extensions.md)), bir iç içe geçmiş sınıf erişim değiştiremezsiniz. Varsayılan Microsoft uzantıları altında (/Ze), bu uyarı ile kullanabilirsiniz.  
  
## <a name="example"></a>Örnek  
  
```  
// C4240.cpp  
// compile with: /W3  
class X  
{  
private:  
   class N;  
public:  
   class N  
   {   // C4240  
   };  
};  
  
int main()  
{  
}  
```