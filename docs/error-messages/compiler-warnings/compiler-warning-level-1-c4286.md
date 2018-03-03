---
title: "Derleyici Uyarısı (düzey 1) C4286 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4286
dev_langs:
- C++
helpviewer_keywords:
- C4286
ms.assetid: 93eadd6c-6f36-413b-ba91-c9aa2314685a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fe82281eccdd781a89f2b06c6f58c941afe2787e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4286"></a>Derleyici Uyarısı (düzey 1) C4286
'type1': taban sınıf ('type2') satır numarasında tarafından yakalandı  
  
 Belirtilen özel durum türü, bir önceki işleyicisi tarafından işlenir. İkinci yakalama türü ilk türünden türetilir. Bir taban sınıfı için özel durumlar türetilmiş bir sınıf için özel durumları yakalar.  
  
## <a name="example"></a>Örnek  
  
```  
//C4286.cpp  
// compile with: /W1  
#include <eh.h>  
class C {};  
class D : public  C {};  
int main()  
{  
    try  
    {  
        throw "ooops!";  
    }  
    catch( C ) {}  
    catch( D ) {}  // warning C4286, D is derived from C  
}  
```