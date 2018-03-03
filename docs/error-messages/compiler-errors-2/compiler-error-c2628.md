---
title: "Derleyici Hatası C2628 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2628
dev_langs:
- C++
helpviewer_keywords:
- C2628
ms.assetid: 19a25e77-d5be-4107-88d5-0745b6281f98
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0284c0ecca016009f6be99faf055c8499a76452c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2628"></a>Derleyici Hatası C2628
'type1 'type2' tarafından izlenen' geçersiz (unuttunuz mu bir ';'?)  
  
 Noktalı virgül eksik olabilir.  
  
 Aşağıdaki örnek C2628 oluşturur:  
  
```  
// C2628.cpp  
class CMyClass {}  
int main(){}   // C2628 error  
```  
  
 Olası çözüm:  
  
```  
// C2628b.cpp  
class CMyClass {};  
int main(){}  
```