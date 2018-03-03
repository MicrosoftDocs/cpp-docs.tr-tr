---
title: "Derleyici Hatası C2825 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2825
dev_langs:
- C++
helpviewer_keywords:
- C2825
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4b907c94b6c83354c139fd3df8b56b1b2287c0b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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