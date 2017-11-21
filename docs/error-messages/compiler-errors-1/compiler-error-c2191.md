---
title: "Derleyici Hatası C2191 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2191
dev_langs: C++
helpviewer_keywords: C2191
ms.assetid: 051b8350-e5de-4f51-ab6e-96d32366bcef
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 8c8f1848fedf7bf811a335043693980855293694
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2191"></a>Derleyici Hatası C2191
İkinci parametre listesi ilk daha uzun  
  
 C işlev daha uzun bir parametre listesi ile ikinci kez bildirildi. C aşırı yüklenmiş işlevlerin desteklemez.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2191 oluşturur:  
  
```  
// C2191.c  
// compile with: /Za /c  
void func( int );  
void func( int, float );   // C2191 different parameter list  
void func2( int, float );   // OK  
```