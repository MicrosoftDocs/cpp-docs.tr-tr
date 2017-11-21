---
title: "Derleyici Hatası C2825 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2825
dev_langs: C++
helpviewer_keywords: C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ebe700fed581eadbab256c9c4f9e2f71bf1d1585
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2825"></a>Derleyici Hatası C2825
var: bir sınıf veya tarafından izlendiğinde ad olmalıdır '::'  
  
 Başarısız bir tam ad oluşturmak için çalışıldı.  
  
 Örneğin, kodunuzu işlev adı ile başladığı bir işlev bildirimi içermediğinden emin olun::.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek C2825 oluşturur:  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```