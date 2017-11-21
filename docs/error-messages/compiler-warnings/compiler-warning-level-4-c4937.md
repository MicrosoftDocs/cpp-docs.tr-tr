---
title: "Derleyici Uyarısı (düzey 4) C4937 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4937
dev_langs: C++
helpviewer_keywords: C4937
ms.assetid: 2bb9f0e7-bbd6-4697-84de-95955e32ae29
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 824eed0550fd684232d829678eae64b1acfa9a37
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4937"></a>Derleyici Uyarısı (düzey 4) C4937
'Metin1' ve 'Metin2' 'yönergesi' bağımsız değişken olarak ayırt  
  
 Yol nedeniyle derleyici yönergeleri, birden çok metin şekillerini (tek ve çift alt çizgi formlar) ile anahtar sözcükler gibi derleyici anlamı, ayırt edici olamaz adları bağımsız değişkenleri işler.  
  
 Bu tür dizeleri örnekler __cdecl ve \__forceinline.  , Yalnızca çift alt çizgi formları etkin /Za altında unutmayın.  
  
 Aşağıdaki örnek C4937 oluşturur:  
  
```  
// C4937.cpp  
// compile with: /openmp /W4  
#include "omp.h"  
int main() {  
   #pragma omp critical ( __leave )   // C4937  
   ;  
  
   // OK  
   #pragma omp critical ( leave )  
   ;  
}  
```