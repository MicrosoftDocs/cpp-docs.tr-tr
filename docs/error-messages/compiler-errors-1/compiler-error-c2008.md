---
title: "Derleyici Hatası C2008 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2008
dev_langs: C++
helpviewer_keywords: C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3edf3320fb8a598e216e716ffdc5c2a1a01d1d6f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2008"></a>Derleyici Hatası C2008
'character': makrosu tanımında beklenmeyen  
  
 Karakter hemen makrosu adı görünür. Hatayı gidermek için bir boşluk makrosu adı olmalıdır sonra.  
  
 Aşağıdaki örnek C2008 oluşturur:  
  
```  
// C2008.cpp  
#define TEST1"mytest1"    // C2008  
```  
  
 Olası çözüm:  
  
```  
// C2008b.cpp  
// compile with: /c  
#define TEST2 "mytest2"  
```