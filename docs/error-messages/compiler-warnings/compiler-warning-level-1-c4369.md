---
title: "Derleyici Uyarısı (düzey 1) C4369 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4369
dev_langs: C++
helpviewer_keywords: C4369
ms.assetid: ade87e84-36be-4e00-be99-2930af848feb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 6e3150b60de6019968680a5a7350f09868dd5564
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4369"></a>Derleyici Uyarısı (düzey 1) C4369
'Numaralandırıcı': Numaralayıcı değeri 'value' 'type' temsil edilemez, değer 'yeni_değer'.  
  
 Belirtilen temel tür için en büyük değerden daha büyük olması için bir numaralandırıcı hesaplanır.  Bu taşmaya neden oldu ve derleyici türü için olası en düşük değer Numaralandırıcı değerine sarılır.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C4369 oluşturur.  
  
```  
// C4369.cpp  
// compile with: /W1  
int main() {  
   enum Color: char { red = 0x7e, green, blue };   // C4369  
   enum Color2: char { red2 = 0x7d, green2, blue2};   // OK  
}  
```