---
title: "Derleyici Uyarısı (düzey 1) C4138 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4138
dev_langs: C++
helpviewer_keywords: C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae173f0862517d7c8d125cc5cf479b84d6463f46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4138"></a>Derleyici Uyarısı (düzey 1) C4138
' * /' yorum dışında bulundu  
  
 Bir açma açıklama sınırlayıcısı açıklaması kapatma sınırlayıcısı öncesinde değil. Yıldız arasında bir boşluk derleyici varsayar (**\***) ve eğik çizgi (/).  
  
## <a name="example"></a>Örnek  
  
```  
// C4138a.cpp  
// compile with: /W1  
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning  
int main()  
{  
}  
```  
  
 Bu uyarı açıklamaları iç içe deneyerek neden olabilir.  
  
 Bu uyarı açıklamaları içeren, kodda içine kod bölümlerini çıkarırsanız çözümlenebilir bir **#if / #endif** engelleme ve denetleme ifade sıfır olarak ayarlayın:  
  
```  
// C4138b.cpp  
// compile with: /W1  
#if 0  
int my_variable;   /* Declaration currently not needed */  
#endif  
int main()  
{  
}  
```