---
title: Derleyici Hatası C2087 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2087
dev_langs:
- C++
helpviewer_keywords:
- C2087
ms.assetid: 89761e83-415a-4468-a4c6-b6dedfd1dd6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8a6012bd49d9d68cbc3318afb390b5f5b411e39f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
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