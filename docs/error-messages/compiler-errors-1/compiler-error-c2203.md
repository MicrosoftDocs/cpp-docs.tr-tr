---
title: "Derleyici Hatası C2203 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2203
dev_langs: C++
helpviewer_keywords: C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebb6260cbf41ffcd48ef60a1bd183e27db17e16a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2203"></a>Derleyici Hatası C2203
Delete işleci, bir dizi sınırları belirtemezsiniz  
  
 İle **/Za** (ANSI) seçeneği `delete` işleci tüm diziyi ancak bölümleri veya dizi belirli üyeleri silebilirsiniz.  
  
 Aşağıdaki örnek C2203 oluşturur:  
  
```  
// C2203.cpp  
// compile with: /Za  
int main() {  
   int *ar = new int[10];  
   delete [4] ar;   // C2203  
   // try the following line instead  
   // delete [] ar;  
}  
```