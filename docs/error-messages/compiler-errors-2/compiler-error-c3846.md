---
title: "Derleyici Hatası C3846 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3846
dev_langs: C++
helpviewer_keywords: C3846
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 58ffd3f240505d173014f1f9b358b4957a41eaf5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3846"></a>Derleyici Hatası C3846
'simgesi': 'assembly2' simgesini alınamıyor: 'simgesi' başka bir derlemeden 'assembly1' içe gibi  
  
 Başvurulan bir derleme önceden içeri aktarılmış olduğundan bir simge başvurulan bir derleme alınamadı.  
  
## <a name="example"></a>Örnek
Aşağıdaki örnek C3846 oluşturur:  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 Ve bu derleme:  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
