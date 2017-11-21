---
title: "Derleyici Uyarısı (düzey 1) C4269 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4269
dev_langs: C++
helpviewer_keywords: C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ee524e998a4d314b7ae3fff74b48b8a6ca6a621f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4269"></a>Derleyici Uyarısı (düzey 1) C4269
'tanımlayıcısı': oluşturulan derleyici varsayılan kurucu ile başlatılmış 'const' otomatik veri güvenilir olmayan sonuçlar üretir  
  
 A **const** otomatik Önemsiz olmayan bir sınıfın örneğini derleyicinin ürettiği varsayılan kurucu ile başlatıldı.  
  
## <a name="example"></a>Örnek  
  
```  
// C4269.cpp  
// compile with: /c /LD /W1  
class X {  
public:  
   int m_data;  
};  
  
void g() {  
   const X x1;   // C4269  
};  
```  
  
 Bu sınıfın örneğini ilk değeri yığında oluşturulan beri `m_data` herhangi bir şey olabilir. Ayrıca, beri olduğu bir **const** örneği, değeri `m_data` hiçbir zaman değiştirilemez.