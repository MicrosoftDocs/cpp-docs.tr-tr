---
title: Derleyici Hatası C2386 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2386
dev_langs:
- C++
helpviewer_keywords:
- C2386
ms.assetid: aaaa1284-34a0-4da2-8547-9fcbb559dae0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5bcbcb3502dba1497500a9bdd5b46345b729a26
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2386"></a>Derleyici Hatası C2386
'simgesi': Bu ada sahip bir sembolü geçerli kapsamda zaten var.  
  
 Ad alanı diğer adı oluşturmayı denedi ancak zaten seçtiğiniz adı yok.  
  
 Aşağıdaki örnek C2386 oluşturur:  
  
```  
// C2386.cpp  
namespace A {  
   int k;  
}  
  
int i;  
namespace i = A;   // C2386, i already exists  
```