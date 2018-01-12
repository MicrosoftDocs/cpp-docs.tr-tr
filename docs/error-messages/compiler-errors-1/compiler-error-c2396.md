---
title: "Derleyici Hatası C2396 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2396
dev_langs: C++
helpviewer_keywords: C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3cabcb0acf6f9b0a476df35de887fc3c9e0efb01
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2396"></a>Derleyici Hatası C2396
' your_type::operator'type'': CLR veya WinRT kullanıcı tanımlı dönüştürme functionnot geçerli. Dönüştür veya Dönüştür: 'T ^', 'T ^ %', 'T ^ &', burada T 'your_type' =  
  
 Windows çalışma zamanı veya yönetilen türü dönüştürme işlevinde türü Dönüşüm işlevini içeren türü ile aynı olan en az bir parametre sahip değil.  
  
 Aşağıdaki örnek C2396 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```