---
title: "Derleyici Uyarısı (Düzey 2) C4156 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4156
dev_langs: C++
helpviewer_keywords: C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4e60e8918d33594df6d362eeed3a195484962d32
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4156"></a>Derleyici Uyarısı (Düzey 2) C4156
dizi biçimi 'Delete'; kullanmadan bir dizi ifadesi silme Değiştirilen dizi biçimi  
  
 Dizi olmayan tür **silme** bir dizi silemezsiniz. Derleyici çevrilen **silmek** dizi form.  
  
 Bu uyarı, yalnızca Microsoft uzantıları altında (/Ze) oluşur.  
  
## <a name="example"></a>Örnek  
  
```  
// C4156.cpp  
// compile with: /W2  
int main()  
{  
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];  
   delete array; // C4156, changed by compiler to "delete [] array;"  
}  
```