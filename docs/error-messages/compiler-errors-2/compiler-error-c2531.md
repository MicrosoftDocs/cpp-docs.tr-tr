---
title: Derleyici Hatası C2531 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2531
dev_langs:
- C++
helpviewer_keywords:
- C2531
ms.assetid: c49afe15-55f8-4dc8-ac01-bf653622a7db
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: af944c56dfd579c608edd48b22925480f16d05c4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33198527"
---
# <a name="compiler-error-c2531"></a>Derleyici Hatası C2531
'tanımlayıcısı': biraz alan geçersiz referansı  
  
 Bit alanları yönelik başvurulara izin verilmez.  
  
 Aşağıdaki örnek C2531 oluşturur:  
  
```  
// C2531.cpp  
// compile with: /c  
class P {  
   int &b1 : 10;   // C2531  
   int b2 : 10;   // OK  
};  
```