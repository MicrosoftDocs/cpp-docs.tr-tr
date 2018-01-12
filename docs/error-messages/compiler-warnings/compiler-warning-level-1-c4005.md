---
title: "Derleyici Uyarısı (düzey 1) C4005 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4005
dev_langs: C++
helpviewer_keywords: C4005
ms.assetid: 7f2dc79a-9fcb-4d5b-be61-120d9cb487ad
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cf0c5777cecf89bb0723b30c87dc4c856de0a016
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4005"></a>Derleyici Uyarısı (düzey 1) C4005
'tanımlayıcısı': makrosu yeniden tanımlama  
  
 Makro tanımlayıcısı iki kez tanımlanır. Derleyici ikinci bir makro tanımı kullanır.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri kontrol ederek düzeltmek için  
  
1.  Komut satırında ve koduyla makro tanımlarken bir `#define` yönergesi.  
  
2.  INCLUDE dosyalarından içeri makrolar.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Aşağıdaki olası çözümlere kullanarak düzeltmek için  
  
1.  Tanımları birini kaldırın.  
  
2.  Kullanım bir [#undef](../../preprocessor/hash-undef-directive-c-cpp.md) ikinci tanımı önce yönergesi.  
  
 Aşağıdaki örnek C4005 oluşturur:  
  
```  
// C4005.cpp  
// compile with: /W1 /EHsc  
#include <iostream>  
using namespace std;  
  
#define TEST "test1"  
#define TEST "test2"   // C4005 delete or rename to resolve the warning  
  
int main() {  
   cout << TEST << endl;  
}  
```