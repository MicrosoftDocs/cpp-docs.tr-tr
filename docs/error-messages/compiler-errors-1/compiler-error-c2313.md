---
title: "Derleyici Hatası C2313 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C2313
dev_langs: C++
helpviewer_keywords: C2313
ms.assetid: f70eb19b-c0a3-4fb2-ade1-3890a589928d
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f0c13aaa35f58a1ecc5ef51750416e86acb4429f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2313"></a>Derleyici Hatası C2313
'type1': satır numarasında ('type2') başvuruya yakalandı  
  
 Özel durum türü iki işleyicileri sahiptir. İkinci yakalama ilk türüne bir başvuru türüdür.  
  
 Aşağıdaki örnek C2313 oluşturur:  
  
```  
// C2313.cpp  
// compile with: /EHsc  
#include <eh.h>  
class C {};  
int main() {  
    try {  
        throw "ooops!";  
    }  
    catch( C& ) {}  
    catch( C ) {}   // C2313  
}  
```