---
title: Derleyici Hatası C2041 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2041
dev_langs:
- C++
helpviewer_keywords:
- C2041
ms.assetid: c9a33bb1-f9cf-47d6-bd21-7d867a8c37d5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 747dd5621aec556e89fee2ab8e7ff512736e408c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33164472"
---
# <a name="compiler-error-c2041"></a>Derleyici Hatası C2041
Geçersiz sayı temel 'numara' için ' character'  
  
 Belirtilen karakter tabanı (örneğin, sekizli veya onaltılı) için geçerli bir sayı değil.  
  
 Aşağıdaki örnek C2041 oluşturur:  
  
```  
// C2041.cpp  
int i = 081;   // C2041  8 is not a base 8 digit  
```  
  
 Olası çözüm:  
  
```  
// C2041b.cpp  
// compile with: /c  
int j = 071;  
```