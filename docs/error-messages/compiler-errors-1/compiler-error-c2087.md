---
title: "Derleyici Hatası C2087 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2087
dev_langs:
- C++
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c177a62939bf46eea24cf26f41a44502f9a70f18
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2087"></a>Derleyici Hatası C2087
'tanımlayıcısı': Eksik alt simge  
  
 Birden çok alt simgeler sahip bir dizi tanımını birden daha yüksek bir boyut için alt simge bir değer eksik.  
  
 Aşağıdaki örnek C2087 oluşturur:  
  
```  
// C2087.cpp  
int main() {  
   char a[10][];   // C2087  
}  
```  
  
 Olası çözüm:  
  
```  
// C2087b.cpp  
int main() {  
   char b[4][5];  
}  
```