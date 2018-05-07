---
title: Derleyici Hatası C2236 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2236
dev_langs:
- C++
helpviewer_keywords:
- C2236
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f755c9ba72e2d36bdce608e93e8a60175e493a45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2236"></a>Derleyici Hatası C2236
beklenmeyen belirteç 'tanımlayıcısı'. Unuttunuz mu bir ';'?  
  
 Tanımlayıcı zaten bir tür olarak tanımlandığından ve kullanıcı tanımlı bir tür tarafından geçersiz kılınamaz.  
  
 Aşağıdaki örnek C2236 oluşturur:  
  
```  
// C2236.cpp  
// compile with: /c  
int class A {};  // C2236 "int class" is unexpected  
int i;  
class B {};  
```