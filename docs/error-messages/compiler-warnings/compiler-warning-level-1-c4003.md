---
title: "Derleyici Uyarısı (düzey 1) C4003 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4003
dev_langs: C++
helpviewer_keywords: C4003
ms.assetid: 0ed1c285-4428-4c90-8131-86897e31f115
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 0e0ac3c216168ada4f2367adbac509b422aba310
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4003"></a>Derleyici Uyarısı (düzey 1) C4003
Makro 'tanımlayıcısı' için gerçek yeterli parametreleri  
  
 Makro tanımı'ndaki biçimsel parametresi sayısı makrosu gerçek parametrelerinde sayısını aşıyor. Eksik parametre için boş metin makrosu genişletme değiştirir.  
  
 Aşağıdaki örnek C4003 oluşturur:  
  
```  
// C4003.cpp  
// compile with: /WX  
#define test(a,b) (a+b)  
  
int main()  
{  
   int a = 1;  
   int b = 2;  
   a = test(b);   // C4003  
   // try..  
   a = test(a,b);  
}  
```