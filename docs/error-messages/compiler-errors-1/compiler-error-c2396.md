---
title: Derleyici Hatası C2396 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2396
dev_langs:
- C++
helpviewer_keywords:
- C2396
ms.assetid: 1b515ef6-7af4-400f-b4ed-564313ea15f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fd9007d15cb5b6f9badf8f0962c8c1aa29df5bf7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33197461"
---
# <a name="compiler-error-c2396"></a>Derleyici Hatası C2396
' your_type::operator'type'': CLR veya WinRT kullanıcı tanımlı dönüştürme functionnot geçerli. Dönüştür veya Dönüştür: 'T ^', 'T ^ %', 'T ^ &', burada T 'your_type' =  
  
 Windows çalışma zamanı veya yönetilen türü dönüştürme işlevinde türü Dönüşüm işlevini içeren türü ile aynı olan en az bir parametre sahip değil.  
  
 Aşağıdaki örnek C2396 oluşturur ve düzeltmek gösterilmektedir:  
  
```  
// C2396.cpp  
// compile with: /clr /c  
  
ref struct Y {  
   static operator int(char c);   // C2396  
  
   // OK  
   static operator int(Y^ hY);  
   // or  
   static operator Y^(char c);  
};  
```