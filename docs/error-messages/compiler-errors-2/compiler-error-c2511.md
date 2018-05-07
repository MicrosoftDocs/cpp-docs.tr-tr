---
title: Derleyici Hatası C2511 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2511
dev_langs:
- C++
helpviewer_keywords:
- C2511
ms.assetid: df999efe-fe2b-418b-bb55-4af6a0592631
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d97cbbd75d3b39b55ff640ed99e261ba349043d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2511"></a>Derleyici Hatası C2511
'tanımlayıcısı': 'sınıfında' bulunamadı üye işlevi aşırı yüklenmiş  
  
 Herhangi bir sürümü işlevi belirtilen parametrelerle bildirildi.  Olası nedenler:  
  
1.  İşlevi için yanlış parametre geçirildi.  
  
2.  Parametreler yanlış sırayla geçirildi.  
  
3.  Parametre adları yanlış yazımını.  
  
 Aşağıdaki örnek C2511 oluşturur:  
  
```  
// C2511.cpp  
// compile with: /c  
class C {  
   int c_2;  
   int Func(char *, char *);  
};  
  
int C::Func(char *, char *, int i) {   // C2511  
// try the following line instead  
// int C::Func(char *, char *) {  
   return 0;  
}  
```