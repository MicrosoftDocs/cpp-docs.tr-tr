---
title: "Derleyici Uyarısı (düzey 1) C4269 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4269
dev_langs:
- C++
helpviewer_keywords:
- C4269
ms.assetid: 96c97bbc-068a-4b65-8cd8-4ed5dca04c15
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e3d276aa5744d457ee987334d65728b1835593ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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