---
title: "Derleyici Hatası C3540 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3540
dev_langs: C++
helpviewer_keywords: C3540
ms.assetid: 3c0c959c-e3b7-40eb-b922-ccac44bd9d85
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0ff7a017ce86e567d0aabcf494e11f48d1cdea05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3540"></a>Derleyici Hatası C3540
'type': sizeof 'auto' içeren bir türü için uygulanamaz  
  
 [Sizeof](../../cpp/sizeof-operator.md) işleci içerdiğinden belirtilen türe uygulanamaz `auto` tanımlayıcısı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3540 verir.  
  
```  
// C3540.cpp  
// Compile with /Zc:auto  
int main() {  
    auto x = 123;  
    sizeof(x);    // OK  
    sizeof(auto); // C3540  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)   
 [/ZC:Auto (değişken türünü)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [sizeof işleci](../../cpp/sizeof-operator.md)