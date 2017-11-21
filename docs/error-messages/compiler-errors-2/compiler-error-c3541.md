---
title: "Derleyici Hatası C3541 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3541
dev_langs: C++
helpviewer_keywords: C3541
ms.assetid: 252cfd4c-5fd2-415e-a17d-6b0c254350db
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 78b4c228999560807aa28dbaecfaa8f0af7b379a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3541"></a>Derleyici Hatası C3541
'type': TypeID 'auto' içeren bir türü için uygulanamaz  
  
 [TypeID](../../windows/typeid-cpp-component-extensions.md) işleci içerdiğinden belirtilen türe uygulanamaz `auto` tanımlayıcısı.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C3541 verir.  
  
```  
// C3541.cpp  
// Compile with /Zc:auto  
#include <typeinfo>  
int main() {  
    auto x = 123;  
    typeid(x);    // OK  
    typeid(auto); // C3541  
    return 0;  
}  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Auto anahtar sözcüğü](../../cpp/auto-keyword.md)   
 [/ZC:Auto (değişken türünü)](../../build/reference/zc-auto-deduce-variable-type.md)   
 [TypeId](../../windows/typeid-cpp-component-extensions.md)