---
title: "Derleyici Hatası C2878 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2878
dev_langs: C++
helpviewer_keywords: C2878
ms.assetid: 83ee3de1-f554-49e8-a840-1f550cee7f69
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ac362394345e144cfb3d50d7886ae8f4aef29c3d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2878"></a>Derleyici Hatası C2878
'name': bir ad alanı veya sınıf adı yok  
  
 Ad alanı veya tanımlı değil sınıfı başvuru yapılmış.  
  
 Aşağıdaki örnek C2878 oluşturur:  
  
```  
// C2878.cpp  
// compile with: /c  
namespace A {}  
namespace B = C;   // C2878 namespace C doesn't exist  
namespace B = A;   
```